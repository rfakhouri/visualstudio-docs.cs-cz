---
title: "Visual Studio Tools for Unity Azure Mobile návod klienta | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5A8762A1-D843-4FD8-A89B-E5E489ECA03D
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 451b4f1f2580a55077bf3fc6a9ad3f16a2afaf0f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="implement-the-azure-mobileserviceclient"></a>Implementace Azure MobileServiceClient

Centrální pro Azure Mobile Client SDK je <a href="https://msdn.microsoft.com/en-us/library/azure/microsoft.windowsazure.mobileservices.mobileserviceclient(v=azure.10).aspx">MobileServiceClient</a>, který umožňuje přístup na váš back-end mobilní aplikace.

## <a name="locate-the-url-of-the-mobile-app-backend"></a>Vyhledejte adresu URL back-end mobilní aplikace

`MobileServiceClient` Konstruktor přebírá adresu URL mobilní aplikace jako parametr, takže před do budoucna, vyhledejte adresu URL.

1. Na portálu Azure klikněte **App Services** tlačítko.

    ![Klikněte na aplikační služby](media/vstu_azure-implement-azure-mobileserviceclient-image1.png)

2. Klikněte na položku pro mobilní aplikace.

    ![Klikněte na mobilní aplikace](media/vstu_azure-implement-azure-mobileserviceclient-image2.png)

3. Zkopírujte adresu URL back-endu mobilní aplikace.

    ![Zkopírujte adresu URL](media/vstu_azure-implement-azure-mobileserviceclient-image3.png)

## <a name="create-the-mobileserviceclient-singleton"></a>Vytvoření jednotlivého prvku MobileServiceClient

Měla by existovat pouze jedna instance `MobileServiceClient`, takže návod používá varianta vzoru singleton.

1. Uvnitř **prostředky nebo skripty** Unity projektu, vytvořte nový skript jazyka C#, s názvem **AzureMobileServiceClient**.

2. Otevřete `AzureMobileServiceClient` skript a odstraňte všechny existující kód šablony, včetně používání příkazů a deklaraci třídy.

3. Přidejte následující kód:

  ```csharp
  using Microsoft.WindowsAzure.MobileServices;

  public static class AzureMobileServiceClient
  {
      private const bool ignoreTls = true;
      private const string backendUrl = "MOBILE_APP_URL";
      private static MobileServiceClient client;

      public static MobileServiceClient Client
      {
          get
          {
              if (client == null)
              {
                  client = new MobileServiceClient(backendUrl);
              }

              return client;
          }
      }
  }
  ```

  > [!NOTE]
  > Pokud IntelliSense nerozpozná Microsoft.WindowsAzure obor názvů, zkontrolujte, že jste dokončili všechny kroky v [Příprava vývojového prostředí]() části.

4. V předchozím kódu, nahraďte `MOBILE_APP_URL` s adresou URL back-endu mobilní aplikace.

## <a name="next-step"></a>Další krok

* [Aktualizace Unity Mono zabezpečení úložiště](visual-studio-tools-for-unity-azure-security.md)
