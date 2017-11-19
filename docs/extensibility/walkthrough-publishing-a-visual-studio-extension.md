---
title: "Návod: Publikování rozšíření sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing web controls
- web controls, publishing
ms.assetid: a7816161-0490-4043-86f5-0f7331ed83b3
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d8eac89a2bdde3b0a20ea3a98775de84a503f86c
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="walkthrough-publishing-a-visual-studio-extension"></a>Návod: Publikování rozšíření sady Visual Studio

Tento návod ukazuje, jak publikovat rozšíření sady Visual Studio pro Visual Studio Marketplace. Když přidáte rozšíření Marketplace, vývojáři mohou použít **rozšíření a aktualizace** a vyhledejte nové a aktualizované rozšíření existuje.

## <a name="prerequisites"></a>Požadavky

 Chcete-li provést tento postup, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

## <a name="create-a-visual-studio-extension"></a>Vytvoření rozšíření sady Visual Studio

V takovém případě budeme používat příponu VSPackage výchozí, ale stejný postup jsou platné pro každý typ rozšíření.

1. Vytvořte VSPackage v jazyce C# s názvem "TestPublish", který má příkaz nabídky. Další informace najdete v tématu [vytváření rozšíření pro první: Hello, World](../extensibility/extensibility-hello-world.md).

## <a name="package-your-extension"></a>Balíček rozšíření

1. Rozšíření vsixmanifest aktualizujte se správnými informacemi o název produktu, autora a verze.

  ![aktualizace rozšíření vsixmanifest](media/update-extension-vsixmanifest.png)

2. Vytváření rozšíření v **verze** režimu. Rozšíření se teď zabalí jako VSIX ve složce \bin\Release.

3. Můžete poklikejte na VSIX ověření instalace.

## <a name="test-the-extension"></a>Testování rozšíření

 Než budete distribuovat rozšíření, vytvořit a otestovat a ujistěte se, že je správně nainstalován v experimentální instanci sady Visual Studio.

1. V sadě Visual Studio spusťte ladění. Chcete-li otevřít experimentální instanci sady Visual Studio.

2. V experimentální instance, přejděte do **nástroje** nabídky a klikněte na tlačítko **rozšíření a aktualizace...** . Rozšíření TestPublish by se měla objevit v prostředním podokně a povolené.

3. Na **nástroje** nabídky, zajistěte, aby se zobrazí příkaz test.

## <a name="publish-the-extension-to-the-visual-studio-marketplace"></a>Publikování rozšíření pro Visual Studio Marketplace

1. Ujistěte se, který jste vytvořili verzi rozšíření, a že je aktuální.

2. Ve webovém prohlížeči, otevřete [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs) webu.

3. V pravém horním rohu klikněte na **přihlášení**.

4. Pomocí účtu Microsoft k přihlášení. Pokud nemáte účet Microsoft, můžete jeden vytvořit v tomto okamžiku.

5. Klikněte na tlačítko **publikování rozšíření**.  To bude přejděte na stránku Správa pro všechna rozšíření.  Pokud nemáte účet vydavatele, zobrazí se výzva k vytvořit v tuto chvíli.

  ![Nahrajte do Marketplace.](media/upload-to-marketplace.png)

6. Vyberte vydavatele, který chcete použít k nahrání rozšíření.  Vydavatelé můžete změnit kliknutím na název vydavatele v levém horním rohu.

  ![Vydavatel změny Marketplace.](media/change-marketplace-publisher.png)

7. V **1: nahrát rozšíření**, můžete odeslat soubor VSIX přímo na Visual Studio Marketplace nebo stačí přidat odkaz na vlastní web. V takovém případě jsme odešlete naše rozšíření TestPublish.vsix.  Přetáhněte rozšíření nebo používat **klikněte na tlačítko** odkaz na soubor vyhledejte.  Rozšíření naleznete ve složce \bin\Release projektu.  Klikněte na tlačítko **pokračovat**.

8. V **2: Zadejte podrobnosti o rozšíření**, některá pole se vyplní automaticky ze souboru source.extension.vsixmanifest z rozšíření.  Další informace o jednotlivých naleznete níže:

    * **Interní název** se použije v adrese URL stránky podrobností rozšíření. Příklad, způsobí publikování rozšíření v části název vydavatele "myname" a zadání interní název, který se má "myextension" adresu URL "marketplace.visualstudio\.com/items?itemName=myname.myextension" pro toto rozšíření stránku s podrobnostmi.
    
    * **Zobrazovaný název** vašeho rozšíření.  Ze souboru source.extension.vsixmanifest Toto je automaticky vyplněna.
   
    * **Verze** počet rozšíření odesíláte.  Ze souboru source.extension.vsixmanifest Toto je automaticky vyplněna.
    
    * **VSIX ID** je jedinečný identifikátor, který Visual Studio používá pro rozšíření.  To je potřeba, pokud chcete mít rozšíření být automaticky aktualizován.  Ze souboru source.extension.vsixmanifest Toto je automaticky vyplněna.
    
    * **Logo** který se použije pro rozšíření.  Automaticky vyplněna bude ze souboru source.extension.vsixmanifest, pokud zadaná.
    
    * **Krátký popis** z jaké jsou vaše rozšíření.  Automaticky vyplněna bude ze souboru source.extension.vsixmanifest.
    
    * **Přehled** je vhodná například snímky obrazovky a podrobné informace o jaké jsou vaše rozšíření.
    
    * **Podporované verze sady Visual Studio** umožňuje zvolíte, jaké verze sady Visual Studio rozšíření budou fungovat na.  Rozšíření se nainstaluje pouze na tyto verze.
    
    * **Podporované edice sady Visual Studio** umožňuje vybrat jednotlivé edice sady Visual Studio rozšíření budou fungovat na.  Rozšíření se nainstaluje pouze na tyto edice.
    
    * **Typ**.  Nejběžnějším typem rozšíření jsou **nástroje**.
    
    * **Kategorie**.  Vyberte až tři, které jsou nejlepší pro rozšíření.
    
    * **Značky** jsou klíčová slova, které pomáhají uživatelům najít rozšíření. Značky může pomoci zvýšit relevanci hledání rozšíření v Marketplace.
    
    * **Ceny kategorie** jsou náklady na toto rozšíření.
    
    * **Úložiště zdrojového kódu** můžete sdílet s komunitou odkaz ke zdrojovému kódu.
    
    * **Povolit otázkám A odpovědím pro rozšíření** umožní uživatelům ponechat dotazy na stránku rozšíření položky.

9. Klikněte na tlačítko **Uložit & Nahrát**. Zobrazí se stránka Správa zpátky do vašeho vydavatele.  Rozšíření ještě nebyla publikována.  K publikování vašeho rozšíření hover přes položku pro rozšíření a klikněte na **...**  a potom **zkontrolujte veřejné**.  Můžete zobrazit, jak se bude rozšíření vypadat na Marketplace výběrem **zobrazit podrobnosti**.  Pro získání čísla, klikněte na **sestavy**.  Chcete-li změnit rozšíření, klikněte na **upravit*.

  ![Rozšíření položky nabídky](media/extension-entry-menu.png)

10. Po kliknutí na **zveřejnit**, toto rozšíření je nyní veřejné.  Hledat Visual Studio Marketplace pro rozšíření.

## <a name="install-the-extension-from-the-visual-studio-marketplace"></a>Nainstalujte rozšíření v sadě Visual Studio Marketplace

Teď, když je publikována rozšíření, nainstalujte ji v sadě Visual Studio a otestovat ji.

1. V sadě Visual Studio na **nástroje** nabídky, klikněte na tlačítko **rozšíření a aktualizace...** .

2. Klikněte na tlačítko **Online** a poté vyhledejte TestPublish.

3. Klikněte na tlačítko **Stáhnout**. Rozšíření se pak naplánuje pro instalaci.

4. K dokončení instalace, zavřete všechny instance sady Visual Studio.

## <a name="removing-the-extension"></a>Odebrání rozšíření

Rozšíření můžete odebrat z Visual Studio Marketplace a z vašeho počítače.

### <a name="to-remove-the-extension-from-the-visual-studio-marketplace"></a>Chcete-li odebrat rozšíření Visual Studio Marketplace

1. Otevřete [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs) webu.

2. V pravém dolním rohu, klikněte na tlačítko **publikovat** rozšíření.  Vyberte vydavatele, který jste použili k publikování TestPublish.  Zobrazí se na výpis pro TestPublish.

3. Pozastavte ukazatel myši nad položku rozšíření a klikněte na **...**  a **odebrat...** Zobrazí se výzva k potvrzení, pokud chcete odebrat rozšíření.  Click **OK**.

### <a name="to-remove-the-extension-from-your-computer"></a>Chcete-li odebrat rozšíření z vašeho počítače

1. V sadě Visual Studio na **nástroje** nabídky, klikněte na tlačítko **rozšíření a aktualizace...** .

2. Vyberte TestPublish a pak klikněte na tlačítko **odinstalovat**. Rozšíření se pak naplánuje pro odinstalaci.

3. K dokončení odinstalace, zavřete všechny instance sady Visual Studio.
