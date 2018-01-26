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
ms.workload: vssdk
ms.openlocfilehash: be1402da1677388712472d4309c40ce767358f7b
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
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

6. Vyberte vydavatele, který chcete použít k nahrání rozšíření.  Vydavatelé můžete změnit kliknutím na názvy vydavatelů uvedené na levé straně.  Klikněte na **nové rozšíření** a vyberte **Visual Studio**.

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

9. Klikněte na tlačítko **Uložit & Nahrát**. Zobrazí se stránka Správa zpátky do vašeho vydavatele.  Rozšíření ještě nebyla publikována.  Publikování rozšíření, klikněte pravým tlačítkem na rozšíření a vyberte **zveřejnit**.  Můžete zobrazit, jak se bude rozšíření vypadat na Marketplace výběrem **zobrazení rozšíření**.  Pro získání čísla, klikněte na **sestavy**.  Chcete-li změnit rozšíření, klikněte na **upravit*.

  ![Rozšíření položky nabídky](media/extension-entry-menu.png)

10. Po kliknutí na **zveřejnit**, toto rozšíření je nyní veřejné.  Hledat Visual Studio Marketplace pro rozšíření.

## <a name="add-additional-users-to-manage-your-publisher-account"></a>Přidat další uživatele spravovat váš účet vydavatele

Marketplace podporuje udělení oprávnění dalším uživatelům přistupovat ke a spravovat účet vydavatele.

1. Přejděte do vydavatele účet, který chcete přidat další uživatelé.

2. Vyberte **členy** a klikněte na **přidat**

  ![Přidat další uživatele](media/add-users.png)

3. Potom můžete zadat e-mailovou adresu uživatele, které chcete přidat a udělte správnou úroveň přístupu v rámci **vyberte roli**.  Můžete zvolit z následujících akcí:

  * **Tvůrce**: uživatel publikování rozšíření, ale nemůže prohlížet nebo spravovat rozšíření, které zveřejnil jiných uživatelů.
  
  * **Čtečka**: uživatel může zobrazit rozšíření, ale nelze publikovat nebo správě rozšíření.
  
  * **Přispěvatel**: uživatel může publikovat a spravovat rozšíření, ale nelze upravit nastavení vydavatele nebo spravovat přístup.
  
  * **Vlastník**: uživatel můžete publikovat a spravovat rozšíření, upravit nastavení vydavatele a spravovat přístup.
  
## <a name="install-the-extension-from-the-visual-studio-marketplace"></a>Nainstalujte rozšíření v sadě Visual Studio Marketplace

Teď, když je publikována rozšíření, nainstalujte ji v sadě Visual Studio a otestovat ji.

1. V sadě Visual Studio na **nástroje** nabídky, klikněte na tlačítko **rozšíření a aktualizace...** .

2. Klikněte na tlačítko **Online** a poté vyhledejte TestPublish.

3. Klikněte na tlačítko **Stáhnout**. Rozšíření se pak naplánuje pro instalaci.

4. K dokončení instalace, zavřete všechny instance sady Visual Studio.

## <a name="remove-the-extension"></a>Odeberte rozšíření

Rozšíření můžete odebrat z Visual Studio Marketplace a z vašeho počítače.

### <a name="to-remove-the-extension-from-the-visual-studio-marketplace"></a>Chcete-li odebrat rozšíření Visual Studio Marketplace

1. Otevřete [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs) webu.

2. V pravém dolním rohu, klikněte na tlačítko **publikovat** rozšíření.  Vyberte vydavatele, který jste použili k publikování TestPublish.  Zobrazí se na výpis pro TestPublish.

3. Klikněte pravým tlačítkem na položku rozšíření a klikněte na tlačítko **odebrat** zobrazí se výzva k potvrzení, pokud chcete odebrat rozšíření.  Click **OK**.

### <a name="to-remove-the-extension-from-your-computer"></a>Chcete-li odebrat rozšíření z vašeho počítače

1. V sadě Visual Studio na **nástroje** nabídky, klikněte na tlačítko **rozšíření a aktualizace...** .

2. Vyberte TestPublish a pak klikněte na tlačítko **odinstalovat**. Rozšíření se pak naplánuje pro odinstalaci.

3. K dokončení odinstalace, zavřete všechny instance sady Visual Studio.
