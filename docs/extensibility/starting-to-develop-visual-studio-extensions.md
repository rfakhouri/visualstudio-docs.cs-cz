---
title: "Spouštění vyvíjet rozšíření Visual Studia | Microsoft Docs"
ms.custom: 
ms.date: 09/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- getting started, Visual Studio integration
- Visual Studio, integration
ms.assetid: 8fe5e2ab-a424-4173-9d39-dd082c4d58d0
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7bc03568465efa022981ade059b0de68019a5978
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="starting-to-develop-visual-studio-extensions"></a>Spouštění vyvíjet rozšíření Visual Studia
Pokud jste nikdy zapsána rozšíření sady Visual Studio před, pravděpodobně máte nějaké otázky. Jsme některé z nejběžnějších těm, které jsou tady uvedené. Pokud nevidíte informace, které hledáte, použijte tlačítka zpětnou vazbu (**byly užitečné tuto stránku?** v dolní části obrazovky) a požádejte o co chcete použít.  
  
## <a name="what-software-do-i-need-to-develop-visual-studio-extensions"></a>Jaký software je nutné vyvíjet rozšíření Visual Studia?  
 Potřebujete-li vyvíjet rozšíření Visual Studia, nainstalujte Visual Studio SDK kromě Visual Studio. Visual Studio SDK můžete nainstalovat jako součást instalace regulární, nebo můžete ho nainstalovat později. Další informace o instalaci sady Visual Studio SDK najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="what-kinds-of-things-can-i-do-with-visual-studio-extensions"></a>Jaké druhy věcí můžete provést pomocí rozšíření Visual Studia  
 Sky je tento limit, pokud jde o představující si různých rozšíření sady Visual Studio. Samozřejmě většina rozšíření mají něco dělat s psaní kódu, ale která nemusí být v případě. Zde je několik příkladů různých druhů rozšíření, která můžete vytvořit:  
  
-   Podporu pro jazyky, které nejsou zahrnuté v sadě Visual Studio, s barevné zvýrazňování syntaxe, IntelliSense a podporu kompilátoru a ladění  
  
-   Kancelářské nástroje, které rozšiřují základní IDE prostředí s další šablony, dialogová okna kódu refaktoringu, nové nebo okna nástrojů  
  
-   Specifické pro doménu Designer pro scénáře, jako je podpora návrhu nebo cloudových dat  
  
 Příklady rozšíření, podívejte se [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs). Mnoho rozšíření jsou open source a Marketplace obsahuje odkazy na jejich úložiště GitHub. 
  
## <a name="which-visual-studio-features-can-i-extend"></a>Funkce sady Visual Studio, které můžete rozšířit?  
 Teoreticky můžete rozšířit jenom o libovolná součást sady Visual Studio: nabídky, panely nástrojů, příkazy, windows, řešení, projekty, editory a tak dále.  
  
 V praxi našli jsme, že funkce, které se většina lidí chcete rozšířit jsou příkazy, nabídek a panelů nástrojů, windows, technologie IntelliSense a projekty. Tady jsou odkazy na příslušné části:  
  
-   [Rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md): přidat svoje vlastní položky pro Visual Studio nabídek a panelů nástrojů. Můžete je používat spustíte nové funkce v sadě Visual Studio nebo aplikace externí pomocné rutiny. Můžete zadat také vlastní zástupce pro vaše položky nabídky.  
  
-   [Rozšíření a přizpůsobení nástrojů Windows](../extensibility/extending-and-customizing-tool-windows.md): rozšířit existující nástroje systému windows nebo vytvořit vlastní nástroj windows. Například můžete přidat nové vlastnosti do **vlastnosti**, nebo můžete vytvořit nové okno nástroje pro přidání dalších funkcí.  
  
-   [Editor a rozšíření služeb jazyk](../extensibility/editor-and-language-service-extensions.md): Přidat vlastní přizpůsobení IntelliSense, zadaná pro jazyky Visual Studio, nebo vytvořte podporu pro nové programovací jazyky. Můžete vytvořit nový příkaz dokončených, návrhy a nové popisy tlačítek QuickInfo. Pomocí žárovek můžete přidat refaktoringu návrhy a kód opravy pro podporu nového programovací jazyky.  
  
-   [Rozšíření projektů](../extensibility/extending-projects.md)  
  
-   [Rozšíření uživatelských nastavení a možností](../extensibility/extending-user-settings-and-options.md)  
  
-   [Rozšíření vlastností a okno Vlastnosti](../extensibility/extending-properties-and-the-property-window.md)  
  
-   [Rozšíření dalších částí sady Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md)  
  
-   [Izolované prostředí sady Visual Studio](../extensibility/visual-studio-isolated-shell.md)  
  
##  <a name="BKMK_ProjectTemplate"></a>Jaké šablony projektů jsou poskytovány VSSDK?  
 Dva hlavní typy rozšíření jsou VSPackages a MEF rozšíření. VSPackage rozšíření se obecně používají pro rozšíření, které používají nebo rozšířit příkazy, nástroje systému windows a projekty. Rozšíření MEF se používají k rozšíření nebo přizpůsobit editoru Visual Studio.  
  
 Pro rozšíření Visual C# a Visual Basic poskytuje VSSDK prázdná šablona projektu VSIX, který můžete použít společně s nové šablony položek, které vytvořit příkazy nabídky okna nástrojů a rozšíření editorů. Tuto šablonu šablony projektů balíčku, fragmenty kódu a artefaktů můžete použít také pro distribuci ostatním uživatelům.  
  
 Pro jazyk C++ poskytne Průvodce VSPackage kódu k přidání příkazy nabídky okna nástrojů a vlastní editory.  
  
 Izolované prostředí šablona se používá k rozšíření v prostředí Visual Studio, který jste vytvoření firemní identity a distribuovat jako vlastní verzi balíčku. Následující témata ukazují, jak začít pracovat s jednotlivými typy rozšíření:  
  
-   Příkazy nabídky: [vytvoření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
-   Nástroje systému windows: [vytváření rozšíření s okno nástroje](../extensibility/creating-an-extension-with-a-tool-window.md)  
  
-   Rozšíření editorů: [vytváření rozšíření pomocí šablony položky editoru](../extensibility/creating-an-extension-with-an-editor-item-template.md)  
  
-   Základní VSPackages: [vytváření rozšíření s VSPackage](../extensibility/creating-an-extension-with-a-vspackage.md)  
  
-   Šablona projektu VSIX: [Začínáme s šablona projektu VSIX](../extensibility/getting-started-with-the-vsix-project-template.md)  
  
-   Izolované prostředí sady Visual Studio: [návod: vytvoření základní aplikace izolované prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)  
  
## <a name="how-do-i-get-my-extension-to-look-like-visual-studio"></a>Získání Moje rozšíření, aby vypadala jako Visual Studio  
 Získat skvělé tipy pro návrh uživatelského rozhraní pro rozšíření v [Visual Studio prostředí pro práci uživatelů](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md).  
  
## <a name="where-can-i-find-examples-of-vssdk-code"></a>Kde najdu příklady kódu VSSDK?  
 Na odkazy uvedené v předchozí části mít podrobné návody, které ukazují, jak můžete implementovat určité funkce. Můžete také vyhledat s otevřeným zdrojem VSSDK ukázky na webu GitHub na [Visual Studio – ukázky](https://github.com/Microsoft/VSSDK-Extensibility-Samples).  
  
## <a name="how-can-i-distribute-my-extension"></a>Jak se dají distribuovat Moje rozšíření?  
 Můžete nainstalovat rozšíření na jiném počítači nebo odeslat přátelům jako soubor VSIX, který nainstalujete poklepáním. Můžete najít další informace o VSIX balíčky v [přesouvání rozšíření Visual Studia](../extensibility/shipping-visual-studio-extensions.md).  
  
 Můžete také publikovat rozšíření na Visual Studio Marketplace, takže je viditelná pro velkého počtu zákazníků Visual Studio. Příklad balení rozšíření Marketplace, naleznete v části [návod: publikování rozšíření Visual Studio](../extensibility/walkthrough-publishing-a-visual-studio-extension.md). Další informace o co musíte udělat pro publikování na webu Marketplace najdete v tématu [produkty a rozšíření pro Visual Studio](/vsts/integrate/ide/extensions/overview).
