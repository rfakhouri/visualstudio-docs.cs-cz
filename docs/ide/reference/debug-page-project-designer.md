---
title: "Stránka ladění, Návrhář projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vb.ProjectPropertiesDebug
helpviewer_keywords:
- Project Designer, Debug page
- Debug page in Project Designer
ms.assetid: ef11eae9-df96-4e20-aabd-2678ba317140
caps.latest.revision: "32"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a16f39d9f9ba6c3e0790a53c85d0824178083953
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="debug-page-project-designer"></a>Stránka Ladění, návrhář projektu
> [!WARNING]
>  Toto téma se nevztahuje na aplikace UWP. V tématu [spustit relaci ladění (jazyka Visual Basic, C#, C++ a XAML)](../../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md) ve službě Windows Dev Center.  
  
 Použití **ladění** stránky **Návrhář projektu** pro nastavení vlastností pro ladění chování v projektu jazyka Visual Basic nebo C#.  
  
 Abyste měli přístup **ladění** vyberte uzel projektu v **Průzkumníku řešení**. Na **projektu** nabídce zvolte *ProjectName***vlastnosti**. Když **Návrhář projektu** se zobrazí, klikněte na tlačítko **ladění** kartě.  
  
## <a name="configuration-and-platform"></a>Konfigurace a platformy  
 Následující možnosti vám umožňují vyberte konfigurace a platformy můžete zobrazit nebo upravit.  
  
 **Konfigurace**  
 Určuje nastavení konfigurace, které chcete zobrazit nebo změnit. Toto nastavení může být **ladění** (výchozí), **verze**, nebo **všechny konfigurace**. Další informace najdete v tématu [ladění a vydání konfigurace projektu](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e).  
  
 **Platforma**  
 Určuje nastavení platformy, které chcete zobrazit nebo změnit. Může zahrnovat volby **libovolný procesor** (výchozí), **x64**, a **x86**. Další informace najdete v tématu [ladění a vydání konfigurace projektu](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e).  
  
## <a name="start-action"></a>Zahájení  
 **Zahájení** označuje položky se spustí, když je ladit aplikace: projektu, vlastní program, adresu URL nebo nic. Ve výchozím nastavení je tato možnost nastavena na **spuštění projektu**. **Spustit akci** nastavení na **ladění** stránka určuje hodnotu `StartAction` vlastnost.  
  
 **Zahájení projektu**  
 Tuto volbu použijte k určení, že ke spustitelnému souboru (pro aplikace pro systém Windows a Konzolová aplikace projekty) by měl být spuštěn, když je ladit aplikace. Tato možnost je vybrána ve výchozím nastavení.  
  
 **Spuštění externího programu**  
 Tuto volbu použijte k určení, že konkrétní program by měl spustit, když je ladit aplikace.  
  
 **Spuštění prohlížeče s adresou URL**  
 Tuto volbu použijte k určení, že konkrétní adresu URL by měly být dostupné, když je ladit aplikace.  
  
## <a name="start-options"></a>Možnosti spuštění  
 **Argumenty příkazového řádku.**  
 Do tohoto textového pole zadejte argumenty příkazového řádku pro ladění.  
  
 **Pracovní adresář**  
 Do tohoto textového pole zadejte adresář, ve kterém bude spouštěna projektu. Nebo klikněte na tlačítko Procházet (**...** ) Chcete-li vybrat adresář.  
  
 **Použití vzdáleného počítače**  
 K ladění aplikací ze vzdáleného počítače, zaškrtněte toto políčko a zadejte cestu ke vzdálenému počítači, do textového pole.  
  
## <a name="enable-debuggers"></a>Povolit ladicí programy  
 **Povolit ladění nespravovaného kódu**  
 Tato možnost určuje, zda je podporováno ladění nativního kódu. Výběrem tohoto zaškrtávacího políčka, pokud provádíte volání objekty modelu COM nebo pokud spuštění vlastní aplikace napsané v nativním kódu, který volá projekt a musí ladění nativního kódu. Zrušte zaškrtnutí tohoto políčka Zakázat ladění nespravovaného kódu. Toto políčko je ve výchozím nastavení zaškrtnuté.  
  
 **Povolit ladění na serveru SQL Server**  
 Vyberte nebo zrušte zaškrtnutí tohoto políčka, pokud chcete povolit nebo zakázat ladění procedur SQL z vaší aplikace Visual Basic. Toto políčko je ve výchozím nastavení zaškrtnuté.  
  
 **Povolit sady Visual Studio proces hostování**  
 Výběrem tohoto zaškrtávacího políčka Povolit proces hostování sady Visual Studio. Toto políčko je ve výchozím nastavení zaškrtnuto. Další informace najdete v tématu [proces hostování (vshost.exe)](../../ide/hosting-process-vshost-exe.md).  
  
 Chcete-li ladit v zóně zabezpečení, musíte povolit tuto možnost a **ladění tuto aplikaci s vybraným nastavením oprávnění** v [rozšířené zabezpečení dialogové okno nastavení](../../ide/reference/advanced-security-settings-dialog-box.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../../debugger/debugging-in-visual-studio.md)   
 [Konfigurace ladění nastavení projektu pro jazyk C#](../../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Nastavení projektu jazyka Visual Basic konfiguraci ladění](../../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Správa vlastností ladění](http://msdn.microsoft.com/en-us/92474d16-e7fe-4fac-9287-6bd6b3a7eb68)   
 [Postupy: ladění aplikace ClickOnce s omezenými oprávněními](../../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Postupy: Vytvoření a úprava konfigurací](../../ide/how-to-create-and-edit-configurations.md)