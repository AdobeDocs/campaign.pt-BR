---
product: Adobe Campaign
title: Integre os SDKs do Campaign ao seu aplicativo
description: Saiba como integrar SDKs do Campaign Android e iOS ao seu aplicativo
version: v8
feature: Push
role: Developer
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: 9f05209e47f35c91720f68d56593812115726817
workflow-type: tm+mt
source-wordcount: '1567'
ht-degree: 32%

---

# Integre os SDKs do Campaign a seu aplicativo {#integrate-campaign-sdk}

Use SDKs do Campaign para iOS e Android para facilitar a integração de seu aplicativo móvel na plataforma Adobe Campaign.

As versões compatíveis com Android e iOS e as versões compatíveis com SDKs do Campaign para o Campaign v8 estão listadas na [Matriz de compatibilidade](../start/compatibility-matrix.md#MobileSDK) .

>[!NOTE]
>
>Como administrador do Campaign, você pode baixar SDKs do Campaign a partir de [Experience Cloud Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html). Para obter mais informações, entre em contato com o [Atendimento ao cliente do Adobe](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).


## Declarar configurações de integração {#declaring-integration-settings}

Para integrar o SDK do Campaign no aplicativo móvel, o administrador funcional deve fornecer as seguintes informações ao desenvolvedor:

* **Uma chave de integração**: para permitir que a plataforma Adobe Campaign identifique o aplicativo móvel.

   >[!NOTE]
   >
   >Essa chave de integração é inserida no console do Adobe Campaign, na guia **[!UICONTROL Information]** do serviço dedicado ao aplicativo móvel. Consulte a [documentação do Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#creating-ios-app).

* **Um URL de rastreamento**: que corresponde ao endereço do servidor de rastreamento do Adobe Campaign.
* **Um URL de marketing**: para ativar a coleta de assinaturas.

* **No Android**:

   ```sql
   Neolane.getInstance().setIntegrationKey("your Adobe mobile app integration key");
   Neolane.getInstance().setMarketingHost("https://yourMarketingHost:yourMarketingPort/");
   Neolane.getInstance().setTrackingHost("https://yourTrackingHost:yourTrackingPort/"); 
   ```

* **No iOS**:

   ```sql
   Neolane_SDK *nl = [Neolane_SDK getInstance];
   [nl setMarketingHost:strMktHost];
   [nl setTrackingHost:strTckHost];
   [nl setIntegrationKey:strIntegrationKey];
   ```

## Integrar SDK do Android

O Android SDK é uma biblioteca jar gravada em JAVA. Ela permite que desenvolvedores do Android se integrem ao Adobe Campaign: registre um novo dispositivo, vincule o dispositivo a um usuário, rastreie o comportamento e muito mais.

Nesta seção, saiba como usar o Android SDK em um aplicativo Android implementando o [Google Firebase Cloud Messaging (FCM)](https://firebase.google.com/docs/cloud-messaging/).

### Configurar FCM

Para usar a notificação por push no Android, você deve ter uma conta FCM, configurar o aplicativo Android para receber a notificação e vincular o aplicativo à conta FCM. Saiba mais em [Documentação do Google](https://firebase.google.com/docs/cloud-messaging/).

Consulte [Documentação do Google](https://firebase.google.com/docs/android/setup) para adicionar o Firebase ao projeto do Android.

Saiba como implementar o FCM no aplicativo em [Documentação do Google](https://firebase.google.com/docs/android/setup).

>[!NOTE]
>
> * Não se esqueça de baixar e adicionar o arquivo google-services.json ao seu projeto.
   >
   > 
* O `apiKey` deve corresponder ao `projectKey` definido no Aplicativo móvel do Adobe Campaign vinculado a este aplicativo Android.


### Configurar o Android SDK

1. **Inicializar o SDK**

   Antes de usar o Android SDK, é necessário inicializá-lo. A inicialização do SDK pode ser feita na função `onCreate` de uma atividade.

   ```sql
   /** Called when the activity is first created. */
   @Override
   public void onCreate(Bundle savedInstanceState)
   {
       super.onCreate(savedInstanceState);
   
       // initialize Campaign SDK
       SharedPreferences settings = getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
       Neolane.getInstance().setIntegrationKey(settings.getString(YourApplicationActivity.APPUUID_NAME, YourApplicationActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(YourApplicationActivity.SOAPRT_NAME, YourApplicationActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(YourApplicationActivity.TRACKRT_NAME, YourApplicationActivity.DFT_TRACKRT));
       ...
   }
   ```

   O `IntegrationKey` deve corresponder ao &#39;IntegrationKey&#39; definido no Aplicativo móvel do Adobe Campaign vinculado a este aplicativo Android.

1. **Registre o dispositivo móvel no servidor Adobe Campaign**

   A função de registro permite:

   * enviar o ID de notificação ou o ID de envio (deviceToken para iOS e registrationID para Android) para o Adobe Campaign.
   * recuperar a chave de conciliação ou o userKey (email ou número de conta, por exemplo)

   Você deve registrar seu dispositivo no Adobe Campaign, na inicialização do aplicativo ou na ação do usuário. Isso pode ser feito facilmente usando o método `registerDevice`.

   ```sql
   public void onClick(View v)
   {
   SharedPreferences settings = this.context.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   EditText mailEdit = (EditText) this.context.findViewById(R.id.editText1);
   
   final String FCMRegistrationId = FirebaseInstanceId.getInstance().getToken();
   if (FCMRegistrationId != null)
       NeoTripActivity.registerOnNeolane(this.context, FCMRegistrationId, mailEdit.getText().toString());
   
   }
   ```

   YourApplicationActivity.java

   ```sql
   public static void registerOnNeolane(final Context ctx, String registrationId, String userKey)
   {
       NeolaneAsyncRunner neolaneAs = new NeolaneAsyncRunner(Neolane.getInstance());
       // Additional Subscription Parameters
       Map<String,Object> additionnalParam = new HashMap<String, Object>();
       additionnalParam.clear();
       SharedPreferences settings = ctx.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
       if (settings.getBoolean(YourApplicationActivity.SUBPARAMEN1_NAME, false))
       {
           additionnalParam.put(settings.getString(YourApplicationActivity.SUBPARAMNAME1_NAME, "") , settings.getString(YourApplicationActivity.SUBPARAMVALUE1_NAME, ""));   
       }
       if (settings.getBoolean(YourApplicationActivity.SUBPARAMEN2_NAME, false))
       {
           additionnalParam.put(settings.getString(YourApplicationActivity.SUBPARAMNAME2_NAME, "") , settings.getString(YourApplicationActivity.SUBPARAMVALUE2_NAME, ""));   
       }
       if ( additionnalParam.isEmpty() )
       {
           additionnalParam = null;
       }
       // Campaign Registration
       neolaneAs.registerDevice(registrationId, userKey, additionnalParam, ctx, new RequestListener() {
       public void onComplete(String e, Object obj)
       {
           Intent upd = new Intent();
           upd.setAction(BROADCAST_NEWREGISTER_ACTION);
           ctx.sendBroadcast(upd);
       }
   
       public void onNeolaneException(NeolaneException e, Object obj)
       {
           sendErrorMsg(e.getErrorString());
       }
   
       public void onIOException(IOException e, Object obj)
       {
           sendErrorMsg(e.getMessage());
       }
   
       public void sendErrorMsg(String err)
       {
           SharedPreferences.Editor edit = ctx.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE).edit();
           edit.putBoolean(YourApplicationActivity.REGISTRATION_ERROR_NEOLANE_KEYNAME, true);
           edit.commit();
           Intent toast = new Intent();
           toast.setAction(BROADCAST_TOAST_DISPLAY_TEXT);
           toast.putExtra("text", "An error happened, please register again (" + err + ")");
           ctx.sendBroadcast(toast);
       }
       });
   }
   ```

1. **Notificar Campanha quando o token do dispositivo móvel do usuário mudar**

   Recomendamos que você use a função `registerDevice` ao chamar a função `onTokenRefresh` para notificar o Adobe Campaign sobre a alteração no token do dispositivo móvel do usuário.

   Por exemplo:

   YourApplicationFirebaseInstanceIDService.java

   ```sql
   package com.android.YourApplication;
   
   import android.content.Context;
   import android.content.SharedPreferences;
   import android.util.Log;
   
   import com.google.firebase.iid.FirebaseInstanceId;
   import com.google.firebase.iid.FirebaseInstanceIdService;
   
   import static android.content.SharedPreferences.*;
   
   public class YourApplicationFirebaseInstanceIDService extends FirebaseInstanceIdService 
   {
       @Override
       public void onTokenRefresh() 
       {
       SharedPreferences settings = getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
       if (!settings.getBoolean(YourApplicationActivity.USE_GCM, false))
           {
           String refreshedToken = FirebaseInstanceId.getInstance().getToken();
           String userKey = settings.getString(YourApplicationActivity.USERKEY_NAME, "");
           Editor edit = settings.edit();
           edit.putString(YourApplicationActivity.FCM_REGISTRATIONID_NAME, refreshedToken);
           edit.commit();
           YourApplicationActivity.registerOnNeolane(this, refreshedToken, userKey);
           }
       }
   }
   ```

1. **Configurar o Firebase Messaging Service**

   Estenda o `FirebaseMessagingService` no retorno de chamada `onMessageReceived` para receber mensagens. Recomendamos que você chame a função `notifyReceive` quando a chamada de retorno `onMessageReceived` for chamada para habilitar o rastreamento da recepção de notificação no dispositivo móvel. No Adobe Campaign, isso é chamado de **print** notificação: essa função deve ser chamada antes de solicitar que o sistema operacional exiba a notificação.

   YourApplicationMessagingService.java

   ```sql
   package com.android.YourApplication;
   
   import android.content.Context;
   import android.content.SharedPreferences;
   import android.os.Bundle;
   import android.util.Log;
   
   import com.google.firebase.messaging.FirebaseMessagingService;
   import com.google.firebase.messaging.RemoteMessage;
   
   import java.util.Iterator;
   import java.util.Map;
   import java.util.Map.Entry;
   
   public class YourApplicationFirebaseMessagingService extends FirebaseMessagingService 
       {
       private static final String TAG = "MyFirebaseMsgService";
   
       @Override
       public void onMessageReceived(RemoteMessage message) 
           {
           Log.d(TAG, "Receive message from: " + message.getFrom());
           Map<String,String> payloadData = message.getData();
           final Bundle extras = new Bundle();
           final Iterator<Entry<String, String>> iter = payloadData.entrySet().iterator();
           while(iter.hasNext())
           {
           final Entry<String, String>  entry =iter.next();
           extras.putString(entry.getKey(), entry.getValue());
           }
   
           SharedPreferences settings = this.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
           String mesg = payloadData.get("_msg");
           String title = payloadData.get("title");
           String url = payloadData.get("url");
           String messageId = payloadData.get("_mId");
           String deliveryId = payloadData.get("_dId");
           YourApplicationActivity.handleNotification(this, mesg, title, url, messageId, deliveryId, extras);
           }
       }   
   ```

   Para o Campaign Android SDK v1.1.1

   ```sql
   public static void handleNotification(Context context, String message, String title, String url, String messageId, String deliveryId, Bundle extras)
   {
       if( message == null ) message = "No Content";
       if( title == null )   title = "No title";
       if( url == null )     url = "http://www.tripadvisor.fr";
       int iconId = R.drawable.notif_neotrip;
   
       // notify Adobe Campaign that a notification just arrived
       SharedPreferences settings = context.getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
       Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   
       NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
       nas.notifyReceive(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
       public void onNeolaneException(NeolaneException arg0, Object arg1) {}
       public void onIOException(IOException arg0, Object arg1) {}
       public void onComplete(String arg0, Object arg1){}
       });
       if (yourApplication.isActivityVisible())
       {
       Log.i("INFO", "The application has the focus" );
       ...
       }
       else
       {
       // notification creation
       NotificationManager notificationManager = (NotificationManager) context.getSystemService(Context.NOTIFICATION_SERVICE);
       Notification notification;
   
       // Activity to start
       Intent notifIntent = new Intent(context.getApplicationContext(), NotificationActivity.class);
       notifIntent.putExtra("notificationText", message);
       notifIntent.putExtra(NotificationActivity.NOTIFICATION_URL_KEYNAME, url);
       notifIntent.putExtra("_dId", deliveryId);
       notifIntent.putExtra("_mId", messageId);
       notifIntent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
       PendingIntent contentIntent = PendingIntent.getActivity(context, 1, notifIntent, PendingIntent.FLAG_UPDATE_CURRENT);
   
       notification = new Notification.Builder(context)
               .setContentTitle(title)
               .setContentText(message)
               .setSmallIcon(iconId)
               .setContentIntent(contentIntent)
               .build();
   
       // launch the notification
       notification.flags |= Notification.FLAG_AUTO_CANCEL;
       notificationManager.notify(1234, notification);
       }
   }
   ```

1. **Rastrear aberturas de mensagens de dados**

   Para mensagens de dados, você pode rastrear quando um usuário clica em uma notificação para abri-la, usando a função `notifyOpening` . A atividade de notificação será criada quando o usuário clicar na notificação (criada durante a chamada de função `onMessageReceived`)

   Para o Campaign Android SDK v1.1.1

   ```sql
   public class NotificationActivity extends Activity {
       public void onCreate(Bundle savedBundle) {
           [...]
           Bundle extra = getIntent().getExtras();
           if (extra != null) {
               // reinit the Campaign sdk
               SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
               Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
               Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));               
               Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   
               // Get the messageId and the deliveryId to perform tracking
               String deliveryId = extra.getString("_dId");
               String messageId = extra.getString("_mId");
   
               if (deliveryId != null && messageId != null) 
               {
                   try {
                   Neolane.getInstance().notifyOpening(messageId, Integer.valueOf(deliveryId));
                   } catch (NeolaneException e) {
                   // ...
                   } catch (IOException e) {
                   // ...
                   }
               }
           }
       }
   }
   ```

1. **Rastrear aberturas e cliques nas mensagens de notificação**

   Para mensagens de notificação, o rastreamento de abertura/clique precisa ser feito com a função `notifyOpening` dentro da atividade de inicialização do aplicativo, conforme abaixo:

   ```sql
   /** Called when the activity is first created. */
   @Override
   public void onCreate(Bundle savedInstanceState)
   {
       super.onCreate(savedInstanceState);
   
       SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
       // initialize Campaign SDK
       Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   ...
   ...
   ...
   
       // Manage opening/receive tracking of message notification
       Intent intent = getIntent();
       Bundle data = intent.getExtras();
       String messageId = null, deliveryId = null;
       if( data != null ) {
       if (data.containsKey("_mId")) messageId = data.get("_mId").toString();
       if (data.containsKey("_dId")) deliveryId = data.get("_dId").toString();
       if ( messageId != null && deliveryId != null) {
           Log.i(TAG, "Notify opening from backgroun click_action");
           NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
           nas.notifyOpening(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_ok));
           }
           });
           nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_ok));
           }
           });
       }
       }
   }
   ```

   >[!NOTE]
   >
   > Um gerenciamento semelhante precisa ser feito se o usuário estiver usando a opção `click_action` dentro da atividade de target.


1. **Receber rastreamento de mensagens de dados**

   Para mensagens de dados, o rastreamento é recebido no nível de chamada `onMessageReceived`. A função &#39;notifyReceive&#39; precisa ser chamada.

   YourApplicationMessagingService.java

   ```sql
   package com.android.YourApplication;
   
   import android.content.Context;
   import android.content.SharedPreferences;
   import android.os.Bundle;
   import android.util.Log;
   
   import com.google.firebase.messaging.FirebaseMessagingService;
   import com.google.firebase.messaging.RemoteMessage;
   
   import java.util.Iterator;
   import java.util.Map;
   import java.util.Map.Entry;
   
   
   public class YourApplicationFirebaseMessagingService extends FirebaseMessagingService {
   private static final String TAG = "MyFirebaseMsgService";
   
   @Override
   public void onMessageReceived(RemoteMessage message) 
       {
           Log.d(TAG, "Receive message from: " + message.getFrom());
           Map<String,String> payloadData = message.getData();
           final Bundle extras = new Bundle();
           final Iterator<Entry<String, String>> iter = payloadData.entrySet().iterator();
           while(iter.hasNext())
           {
           final Entry<String, String>  entry =iter.next();
           extras.putString(entry.getKey(), entry.getValue());
           }
   
           SharedPreferences settings = this.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
           String mesg = payloadData.get("_msg");
           String title = payloadData.get("title");
           String url = payloadData.get("url");
           String messageId = payloadData.get("_mId");
           String deliveryId = payloadData.get("_dId");
           YourApplicationActivity.handleNotification(this, mesg, title, url, messageId, deliveryId, extras);
       }
   }
   ```

   ```sql
   public static void handleNotification(Context context, String message, String title, String url, String messageId, String deliveryId, Bundle extras){
       .....
       .....
           // notify Campaign that a notification just arrived
           SharedPreferences settings = context.getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
           Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
           Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
           Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   
           NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
           nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
               public void onNeolaneException(NeolaneException arg0, Object arg1) {}
               public void onIOException(IOException arg0, Object arg1) {}
               public void onComplete(String arg0, Object arg1){}
       });
   }
   ```

1. **Receber rastreamento de mensagens de notificação**

   Para mensagens de notificação, o recebimento de rastreamento deve ser configurado em dois níveis:

   * `onMessageReceived` (pedido não apresentado em segundo plano): a implementação foi feita na seção anterior
   * `onCreate` da atividade de inicialização (ou da atividade de target, se a  `click_action`função for usada). (Aplicativo não em segundo plano).

   Isso precisa ser feito ao mesmo tempo que o rastreamento de abertura/clique.

   ```sql
   /** Called when the activity is first created. */
       @Override
       public void onCreate(Bundle savedInstanceState)
       {
           super.onCreate(savedInstanceState);
   
           SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
           // initialize Campaign SDK
           Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
           Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
           Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   ...
   ...
   ...
   
       // Manage opening/receive tracking of message notification
       Intent intent = getIntent();
       Bundle data = intent.getExtras();
       String messageId = null, deliveryId = null;
       if( data != null ) {
       if (data.containsKey("_mId")) messageId = data.get("_mId").toString();
       if (data.containsKey("_dId")) deliveryId = data.get("_dId").toString();
       if ( messageId != null && deliveryId != null) {
           Log.i(TAG, "Notify opening from backgroun click_action");
           NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
           nas.notifyOpening(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_ok));
           }
           });
           nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_ok));
           }
           });
       }
       }
   }
   ```


## Integrar SDK do iOS

1. **Registre o dispositivo móvel no servidor Adobe Campaign**

   A função de registro permite:

   * enviar o ID de notificação ou o ID de envio (deviceToken para iOS e registrationID para Android) para o Adobe Campaign.
   * recuperar a chave de conciliação ou o userKey (email ou número de conta, por exemplo)

   ```sql
   // Callback called on successful registration to the APNs
    - (void)application:(UIApplication*)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData*)deviceToken
   {
     // Pass the token to Adobe Campaign
     Neolane_SDK *nl = [Neolane_SDK getInstance];
     [nl registerDevice:tokenString:self.userKey:dic];
   }
   ```

1. **Habilitar função de rastreamento**

   A função de rastreamento permite rastrear quando as notificações são ativadas (abertas).

   ```sql
   (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions
   fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler
   {
   if( launchOptions ) { // Retrieve notification parameters here ... // Track application opening Neolane_SDK
   *nl = [Neolane_SDK getInstance]; [nl track:launchOptions:NL_TRACK_CLICK]; } 
   ...  
   completionHandler(UIBackgroundFetchResultNoData);
   }
   ```

1. **Rastreamento de notificação silenciosa**

   O iOS permite enviar notificações silenciosas, uma notificação ou dados que são enviados diretamente para um aplicativo móvel sem exibi-los. O Adobe Campaign permite rastreá-las.

   Para rastrear a notificação silenciosa, siga o exemplo abaixo:

   ```sql
   // AppDelegate.m
   ...
   ...
   #import "AppDelegate.h"
   #import "Neolane_SDK.h"
   ...
   ...
   // Callback called when the application is already launched (whether the application is running foreground or background)
   - (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler
   {
   NSLog(@"IN didReceiveRemoteNotification:fetchCompletionHandler");
   if (launchOptions) NSLog(@"IN launchOptions: %@", [launchOptions description]);
   NSLog(@"Application state: %ld", (long)application.applicationState);
   
   // Silent Notification (specific case, can use NL_TRACK_RECEIVE as the user does not have click/open the notification)
   if ([launchOptions[@"aps"][@"content-available"] intValue] == 1 )
       {
   NSLog(@"Silent Push Notification");
   ...  
   ...
   //Call receive tracking
           Neolane_SDK *nl = [Neolane_SDK getInstance];
   [nl track:launchOptions:NL_TRACK_RECEIVE];
   
   completionHandler(UIBackgroundFetchResultNoData); //Do not show notification
   return;
   }  
   ...
   ...
           completionHandler(UIBackgroundFetchResultNoData);
   }
   ```

1. **Configurar o status de registro**

   O protocolo delegado permite obter o resultado da chamada **registerDevice** e pode ser usado para saber se ocorreu um erro durante o registro.

   O protótipo **registerDeviceStatus** é:

   ```sql
   - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status:(NSString *) errorReason;
   ```

   * **Status** permite saber se um registro foi bem-sucedido ou se ocorreu um erro.

   * **ErrorReason** fornece mais informações sobre os erros que ocorreram. Para obter mais informações sobre erros disponíveis e suas descrições, consulte a tabela abaixo.

| Status | Descrição | ErrorReason |
| ---------------------------------------------------------- | ------------------------------------------------------ | ----------------------------------------- |
| ACCRegisterDeviceStatusSuccess | Registration Succeeded | EMPTY |
| ACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty | O nome de host do servidor de marketing ACC está vazio ou não está definido. | EMPTY |
| ACCRegisterDeviceStatusFailureIntegrationKeyEmpty | A chave de integração está vazia ou não está definida. | EMPTY |
| ACCRegisterDeviceStatusFailureConnectionIssue | Problema de conexão com o ACC | Mais informações (na linguagem atual do SO) |
| ACCRegisterDeviceStatusFailureUnknownUUID | O UUID fornecido (chave de integração) é desconhecido. | EMPTY |
| ACCRegisterDeviceStatusFailureUnexpectedError | Erro inesperado retornado ao servidor ACC. | A mensagem de erro retornou para o ACC. |

{style=&quot;table-layout:auto&quot;}

    **O protocolo Neolane_SDKDelegate** e a definição do delegado **registerDeviceStatus** é a seguinte: 
    
    &quot;sql
    // Neolane_SDK.h
    // SDK
     do Campaign.
    ..
    // Registrar Status do Dispositivo 
    Enumtypedef NS_ENUM(NSUInteger, ACCRegisterDeviceStatus) {
    ACCRegisterDeviceStatusSuccess, // Regration 
    SucceedACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty, // O host do servidor de marketing da campanha name is Empty or not 
    setACCRegisterDeviceStatusFailureIntegrationKeyEmpty, // A chave de integração está vazia ou não 
    setACCRegisterDeviceStatusFailureConnectionIssue // Problema de conexão com o Campaign, mais informações em 
    errorReasonACCRegisterDeviceStatusFailureUnknownUUID, // O UUID fornecido (chave de integração) é 
    unknownACCRegisterDeviceStatusFailureUnestimatedError // Erro inesperado retornado pelo servidor do Campaign, mais informações em errorReason
    };
    // defina o protocolo para o delegado registerDeviceStatus
    @protocol Neolane_SDKDelegate  &lt;nsobject>
    @optional
    - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status :(NSString *) errorReason; 
    @end
    @interface Neolane_SDK: NSObject {
    }
    ..
    ...
    // registerDeviceStatus delegate
    @property (não atômico, fraco) id  &lt;neolane_sdkdelegate> delegate;
    ...
    ...
    @end
    &quot;
    
    Para implementar o delegado **registerDeviceStatus**, siga estas etapas:
    
    1. Implemente o **setDelegate** durante a inicialização do SDK.
    
    &quot;sql
    / AppDelegate.m
    ...
    ...
    - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
    {
    ...
    ...
    // Obtenha as 
    
    configurações armazenadasNSUserDefaults *defaults = [NSUserDefaults standardUserDefaults];
    NSString *strMktHost = [defaults objectForKey:@&quot;mktHost&quot;];
    NSString *strTckHost = [defaults objectForKey:@ trackHost&quot;];
    NSString *strIntegrationKey = [defaults objectForKey:@&quot;integrationKey&quot;];
    userKey = [defaults objectForKey:@&quot;userKey&quot;];
    
    // Configurar SDK do Campaign na primeira 
    inicializaçãoNeolane_SDK *nl = [Neolane_SDK getInstance];
     nl setMarketingHost:strMktHost];
    [nl setTrackingHost:strTckHost];
    [nl setIntegrationKey:strIntegrationKey];
    [nl setDelegate:self]; // AQUI
    ...
    ...
    }
    &quot;
    
    1. Adicione o protocolo na **@interface* de sua classe.
    
    &quot;sql
    // AppDelegate.h
    
    #import  &lt;uikit>
    #import  &lt;corelocation>
    #import &quot;Neolane_SDK.h&quot; 
    
    @class LandingPageViewController;
    
    @interface AppDelegate : UIResponder  &lt;uiapplicationdelegate> {
    CLLocationManager *locationManager;
    NSString *userKey;
    NSString *mktServerUrl;
    NSString *tckServerUrl;
    NSString *homeURL;
    NSString *strLandingPageUrl;
    NST Mal *temporizador;
    }
    &quot;
    
    1. Implemente o delegado no **AppDelegate**.
    
    &quot;sql
    / AppDelegate.m
    
    #import &quot;AppDelegate.h&quot; 
    #import &quot;Neolane_SDK.h&quot; 
    #import &quot;LandingPageViewController.h&quot; 
    #import &quot;RootViewController.h&quot;
    ..
    ...
    - (void) registerDeviceStatus: Status (ACCRegisterDeviceStatus) :(NSString *) errorReason
    {
    NSLog(@&quot;registerStatus: %lu&quot;, status); 
    
    if ( errorReason != nil )
    NSLog(@&quot;errorReason: %@&quot;,errorReason);
    
    if( status == ACCRegisterDeviceStatusSuccess )
    {
    / Registro bem-sucedido
    ..
    ..
    }
    else { // Um erro ocorreu
    NSString *message;
    switch ( status ){
    caso ACCRegisterDeviceStatusFailureUnknownUUID:
    message = @&quot;Unkown IntegrationKey (UUID)&quot;;&lt;a1 2/>break;
    caso ACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty:
    message = @&quot;URL de marketing não definido ou vazio&quot;;
    break;
    caso ACCRegisterDeviceStatusFailureIntegrationKeyEmpty: mensagem = @&quot;Chave de integração não definida ou vazia&quot;;
    break;
    caso ACCRegisterDeviceStatusFailureConnectionIssue:
    message = [NSString stringWithFormat:@&quot;%@ %@&quot;,@&quot;Problema de conexão:&quot;,errorReason];&lt;a 21/>break;
    caso ACCRegisterDeviceStatusFailureUnestimatedError:
    default:
    message = [NSString stringWithFormat:@&quot;%@ %@&quot;,@&quot;Erro Inesperado&quot;,errorReason];
    break; 26/>}
    ...
    ...
    }
    }
    @end
    &quot;

    
    
    
    
## Variáveis {#variables}

As variáveis permitem definir o comportamento do aplicativo móvel após receber uma notificação. Essas variáveis devem ser definidas no código do aplicativo móvel e no console do Adobe Campaign, na guia **[!UICONTROL Variables]** no serviço de aplicativo móvel dedicado.

[!DNL :arrow_upper_right:] Saiba mais na documentação do  **Campaign Classic v7** sobre aplicativos móveis:  [Etapas de configuração para ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html) iOSe Etapas  [de configuração para Andoid](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html).

Abaixo está um exemplo de um código que permite que um aplicativo móvel colete quaisquer variáveis adicionadas em uma notificação. No nosso exemplo, estamos usando a variável &quot;VAR&quot;.

* **No Android**:

   ```sql
   public void onReceive(Context context, Intent intent) {
        ...
       String event = intent.getStringExtra("VAR");
        ...
   }
   ```

* **No iOS**:

   ```sql
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
   {
       ....
       if( launchOptions )
       {
           // When application is not already launched, the notification data if any are stored in the key 'UIApplicationLaunchOptionsRemoteNotificationKey'
           NSDictionary *localLaunchOptions = [launchOptions objectForKey:@"UIApplicationLaunchOptionsRemoteNotificationKey"];
           if( localLaunchOptions )
           {
            ...
            [localLaunchOptions objectForKey:@"VAR"];
           ...
           }
      }
   }
   
   // Callback called when the application is already launched (whether the application is running foreground or background)
   - (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions
   {
       if( launchOptions )
       {
        ...
           [launchOptions objectForKey:@"VAR"];
       }
   }
   ```

>[!CAUTION]
>
>A Adobe recomenda escolher nomes de variáveis curtos, pois o tamanho da notificação é limitado a 4kB para iOS e Android.

## Extensão de serviço de notificação {#notification-service-extension}

**Para iOS**

A mídia deve ser baixada no nível da extensão de serviço de notificação.

```sql
#import "NotificationService.h"

@interface NotificationService ()

@property (nonatomic, strong) void (^contentHandler)(UNNotificationContent *contentToDeliver);
@property (nonatomic, strong) UNMutableNotificationContent *bestAttemptContent;

@end

@implementation NotificationService

- (void)didReceiveNotificationRequest:(UNNotificationRequest *)request withContentHandler:(void (^)(UNNotificationContent * _Nonnull))contentHandler {
    NSDictionary *userInfo = nil;
    NSString *url = nil;

    self.contentHandler = contentHandler;
    self.bestAttemptContent = [request.content mutableCopy];

    userInfo = request.content.userInfo;
    if ( userInfo != nil )
    {
        url = userInfo[@"mediaUrl"];  // Get the url of the media to download (Adobe Campaign additional variable)
    }
    ...
    // Perform the download to local storage
```

## Extensão de conteúdo de notificação {#notification-content-extension}

**Para iOS**

Nesse nível, você precisa:

* Associe sua extensão de conteúdo à categoria enviada pelo Adobe Campaign:

   Se quer que seu aplicativo móvel exiba uma imagem, é possível definir o valor da categoria como &quot;imagem&quot; no Adobe Campaign e no aplicativo móvel, criar uma extensão de notificação com o parâmetro **UNNotificationExtensionCategory** definido como &quot;imagem&quot;. Quando a notificação por push é recebida no dispositivo, a extensão é chamada de acordo com o valor da categoria definida.

* Definir o seu layout de notificação

   É necessário definir um layout com os widgets relevantes. Para uma imagem, o widget é denominado **UIImageView**.

* Exibir sua mídia

   É necessário adicionar o código para alimentar os dados de mídia no widget. Veja um exemplo de código para uma imagem:

   ```sql
   #import "NotificationViewController.h"
   #import <UserNotifications/UserNotifications.h>
   #import <UserNotificationsUI/UserNotificationsUI.h>
   
   @interface NotificationViewController () <UNNotificationContentExtension>
   
   @property (strong, nonatomic) IBOutlet UIImageView *imageView;
   @property (strong, nonatomic) IBOutlet UILabel *notifContent;
   @property (strong, nonatomic) IBOutlet UILabel *label;
   
   @end
   
   @implementation NotificationViewController
   
   - (void)viewDidLoad {
       [super viewDidLoad];
       // Do any required interface initialization here.
   }
   
   - (void)didReceiveNotification:(UNNotification *)notification {
       self.label.text = notification.request.content.title;
       self.notifContent.text = notification.request.content.body;
       UNNotificationAttachment *attachment = [notification.request.content.attachments objectAtIndex:0];
       if ([attachment.URL startAccessingSecurityScopedResource])
       {
         NSData * imageData = [[NSData alloc] initWithContentsOfURL:attachment.URL];
         self.imageView.image =[UIImage imageWithData: imageData];
         [attachment.URL stopAccessingSecurityScopedResource];
       }
   }
   @end
   ```
