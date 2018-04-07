---
title: Připojené služby v sadě Visual Studio pro Mac | Microsoft Docs
description: Přidání úložiště dat Azure, ověřování a nabízených oznámení do mobilních aplikací v sadě Visual Studio pro Mac
ms.prod: xamarin
ms.assetid: 41CB62FF-0F39-4CE8-8917-6A77F058719F
author: asb3993
ms.author: amburns
ms.date: 04/04/2018
ms.openlocfilehash: cff322e25e19179ae7da79585d8880ce7565936a
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/06/2018
---
# <a name="connected-services-walkthrough"></a>Návod připojených služeb

Pracovní postup připojení služby Azure pracovního postupu portálu přenese do sady Visual Studio pro Mac, takže není nutné opustit projektu na přidání služeb.

Tento návod ukazuje, jak přidat Azure back-end službu, která přináší datové úložiště v cloudu, ověřování a odesílání nabízených oznámení do aplikace Xamarin.Forms přenosných třída knihovny PCL () různých platformách.


1.  Spusťte dvojitým kliknutím na **připojené služby** uzlu v řešení, které se otevře **služby Galerie**.
  Toto je seznam všech služeb, které jsou k dispozici pro typ aplikace. Vyberte službu (například **mobilního back-endu službou Azure App Service**) kliknutím na.

    [![Uzel připojených služeb v sadě Visual Studio pro Mac](media/connected-services-image001-sml.png "uzlu připojení služby v sadě Visual Studio pro Mac")](media/connected-services-image001.png#lightbox)

2. Stránce s podrobnostmi o službu má popis služby a závislosti k instalaci.
  Klikněte **přidat** tlačítko přidejte závislosti do aplikace:

    [![Mobilní back-end pomocí Azure](media/connected-services-image002-sml.png "mobilní back-end v Azure")](media/connected-services-image002.png#lightbox)

3. Závislosti nutné přidat PCL a specifické pro platformu projekty fungovat.
  Vyberte zaškrtávací políčka pro přidání služby pro každý projekt, který bude odkazovat ho (přímo ani nepřímo):

    [![Zkontrolujte všechny projekty, které by měl odkazovat službu](media/connected-services-image003-sml.png "zkontrolujte všechny projekty, které by měla odkazovat služby")](media/connected-services-image003.png#lightbox)

4. Zvolte **přijmout** na **přijetí licence** dialogová okna pro balíčky NuGet.
  Mohou existovat dvě dialogová okna tak, aby přijímal, jeden pro MobileClient a závislosti a druhý pro SQLiteStore, což je vyžadováno pro synchronizaci dat offline:

    [![Přijměte licenční smlouvy](media/connected-services-image004-sml.png "přijmout licenční smlouvy")](media/connected-services-image004.png#lightbox)

    ![Okno přijetí licenční](media/connected-services-image005.png "okno přijetí licence")

5. Jakmile jsou přidány závislosti, budete vyzváni k přihlášení pomocí účtu, který chcete použít ke komunikaci s Azure.
  Pokud jste již přihlášení ID služeb Microsoft, Visual Studio pro Mac se pokusí načíst vašich předplatných Azure a všechny aplikace služby s nimi spojených. Pokud nemáte žádné předplatné, můžete přidat jeden registrací k bezplatné zkušební verze nebo zakoupení plán předplatného na portálu Azure.

6. Vyberte aplikační službu ze seznamu. Tato hodnota se vyplní kód šablony pro `MobileServiceClient` objekt se adresa URL odpovídajícího v Azure app service:

    [![Vyberte služby app service ze seznamu](media/connected-services-image006-sml.png "seznamu vyberte aplikační služby")](media/connected-services-image006.png#lightbox)

    Pokud neexistují uvedené služby, klikněte **nový** tlačítko (viz krok 9.)

7. Zkopírujte kód šablony pro `MobileServiceClient` do PCL. Umístění souboru není důležité, tak dlouho, dokud je jenom jednu instanci.
  Doporučuje se vytvořit `AzureService` třídu, která zpracovává všechny interakce Azure a používá `MobileServiceClient`:

    ![Zkopírujte konfigurační kód do přístupového bodu](media/connected-services-image007.png "zkopírujte kód konfigurace do aplikace")

8. Postupujte podle dokumentace v **další kroky** přidat data, offline synchronizace, ověřování a nabízená oznámení do vaší aplikace:

    [![Projít pokyny pro další kroky](media/connected-services-image008-sml.png "projít pokyny pro další kroky")](media/connected-services-image008.png#lightbox)

9. Pokud nemáte žádné existující služby, aplikace, můžete vytvořit nové služby z v sadě Visual Studio for Mac.
  Klikněte na tlačítko **nový** tlačítko v levé dolní části seznamu služeb otevřete **nové služby App Service** dialogové okno:

    [![Vytvoření nové aplikace služby v sadě Visual Studio pro Mac](media/connected-services-image009-sml.png "vytvoření nové aplikace služby v sadě Visual Studio pro Mac")](media/connected-services-image009.png#lightbox)

Nová služba vyžaduje následující parametry:

-   **Název služby App service** – jedinečný název nebo id plánu
-   **Předplatné** – předplatné, které chcete použít k platbě za službu
-   **Skupina prostředků** – stejným způsobem jako nebo uspořádání všechny prostředky Azure pro projekt. Možnost použít existující nebo vytvořte novou. Pokud je to první službě Azure, vytvořte novou.
-   **Plánování služby** – Určuje umístění a náklady na všechny prostředky, které ho používají. Možnost použít existující nebo vytvořte novou. Pokud je to první službě Azure, použijte výchozí nastavení nebo vytvořte novou v úrovni free (F1).

Přejděte [dokumentaci služby Azure App Service](https://azure.microsoft.com/documentation/learning-paths/appservice-mobileapps/) Další informace.
