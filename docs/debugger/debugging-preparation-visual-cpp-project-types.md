---
title: 'Příprava na ladění: Typy projektů Visual C++ | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- project templates, debugging
- Visual C++ projects, debugging
- debug builds, project settings
- debugging [C++]
ms.assetid: 912b4ba2-7719-43d5-b087-db33e3f9329a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 64d49d799c0ec0b3845a262c248d2438572ecd5d
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="debugging-preparation-visual-c-project-types"></a>Příprava ladění: typy projektů jazyka Visual C++
Tato část popisuje postup ladění typy základní projektů vytvořených [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] šablony projektu.  
  
 Všimněte si, že tyto typy projektů, které jako jejich výstup vytvořit knihovny DLL, byly seskupeny do [ladění projektů knihovny DLL](../debugger/debugging-dll-projects.md) z důvodu běžné funkce sdílejí.  
  
##  <a name="BKMK_In_this_topic"></a> V tomto tématu  
 [Doporučené nastavení vlastností](#BKMK_Recommended_Property_Settings)  
  
 [Projekty Win32](#BKMK_Win32_Projects)  
  
-   [Chcete-li ladit aplikace C nebo C++ Win32](#BKMK_To_debug_a_C_or_C___Win32_application)  
  
-   [Chcete-li ručně nastavit konfiguraci ladění](#BKMK_To_manually_set_a_Debug_configuration)  
  
 [Aplikace Windows Forms (.NET)](#BKMK_Windows_Forms_Applications___NET_)  
  
##  <a name="BKMK_Recommended_Property_Settings"></a> Doporučené nastavení vlastností  
 Některé vlastnosti musí být nastaven stejným způsobem jako pro všechny nespravované ladění scénáře. Následující tabulky obsahují doporučené nastavení vlastností. Mezi typy jiný nespravované projekt se mohou lišit nastavení, které zde nejsou uvedeny. Další informace najdete v tématu [nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)  
  
### <a name="configuration-properties-124-cc-124-optimization-node"></a>Vlastnosti konfigurace &#124; C/C++ &#124; optimalizace uzlu  
  
|Název vlastnosti|Nastavení|  
|-------------------|-------------|  
|**Optimalizace**|Nastavte na **zakázané (nebo 0 d).** Optimalizovaný kód je těžší ladit, protože vygenerovaný pokyny neodpovídají přímo ke zdrojovému kódu. Pokud zjistíte chybu, která se zobrazí pouze v optimalizovaný kód má program, můžete zapnout toto nastavení, ale mějte na paměti, tento kód ukazuje **zpětný překlad** okno se generují z optimalizované zdroj, který nemusí odpovídat co vidíte ve zdroji Windows. Další funkce, jako je například krokování, nemusí chovat podle očekávání.|  
  
### <a name="configuration-properties-124-linker-124-debugging-node"></a>Vlastnosti konfigurace &#124; Linkeru &#124; uzlu ladění  
  
|Název vlastnosti|Nastavení|  
|-------------------|-------------|  
|**Generovat ladicí informace**|Tato možnost by měla vždy nastavená na **Ano (/ DEBUG)** vytvořit ladění symboly a soubory potřebné pro ladění. Pokud aplikace přejde do produkčního prostředí, můžete nastavit ho vypnout.|  
  
 [V tomto tématu](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)  
  
##  <a name="BKMK_Win32_Projects"></a> Projekty Win32  
 Win32 – aplikace jsou napsané v C nebo C++ tradiční programy systému Windows. Ladění tento typ aplikace v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je jednoduché.  
  
 Aplikace Win32 zahrnují aplikace MFC a projekty knihovny ATL. Kdy použít rozhraní API systému Windows a může pomocí knihovny MFC nebo ATL, ale nepoužívají common language runtime (CLR). Můžou však volat spravovaného kódu, který používá modulu CLR.  
  
 Následující postup vysvětluje, jak k ladění projektu Win32 v rámci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Dalším způsobem ladění aplikace Win32, je-li spustit aplikaci mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a k němu připojí. Další informace najdete v tématu [přiřadit běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
###  <a name="BKMK_To_debug_a_C_or_C___Win32_application"></a> Chcete-li ladit aplikace C nebo C++ Win32  
  
1.  Otevřete projekt v sadě Visual Studio.  
  
2.  Na **ladění** nabídce zvolte **spustit**.  
  
3.  Ladění pomocí technik popsaných v [základy ladicího programu](../debugger/debugger-basics.md).  
  
###  <a name="BKMK_To_manually_set_a_Debug_configuration"></a> Chcete-li ručně nastavit konfiguraci ladění  
  
1.  Na **zobrazení** nabídky, klikněte na tlačítko **stránky vlastností**.  
  
2.  Klikněte **vlastnosti konfigurace** uzlu a otevře se, pokud ještě není  
  
3.  Vyberte **Obecné**a nastavte hodnotu **výstup** řádek na **ladění**.  
  
4.  Otevřete **C/C++** uzel a vyberte možnost **Obecné**.  
  
     V **ladění** řádek zadejte typ ladění informace, které lze generovat kompilátoru. Možné hodnoty patří **databázi programu (/Zi)** nebo **databázi programu pro upravit a pokračovat (/ZI)**.  
  
5.  Vyberte **optimalizace**a v **optimalizace** řádek, vyberte **zakázané (nebo 0d)** z rozevíracího seznamu.  
  
     Optimalizovaný kód je těžší ladit, protože vygenerovaný pokyny neodpovídají přímo ke zdrojovému kódu. Pokud zjistíte, že má program chybu, která se zobrazí pouze v optimalizovaný kód, můžete zapnout toto nastavení, ale mějte na paměti, že kód zobrazený v okně zpětný překlad se generují z optimalizované zdroj, který nemusí odpovídat najdete v v systému windows. zdroj. Funkce, jako je zanoříte se pravděpodobně zobrazit zarážky a provádění bod nesprávně.  
  
6.  Otevřete **Linkeru** uzel a vyberte možnost **ladění**. V prvním **generování** řádek, vyberte **Ano (/ DEBUG)** z rozevíracího seznamu. Vždy nastaven to při ladění.  
  
 Další informace najdete v tématu[nastavení projektu pro konfiguraci ladění C++](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
 [V tomto tématu](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)  
  
##  <a name="BKMK_Windows_Forms_Applications___NET_"></a> Aplikace Windows Forms (.NET)  
 **Windows Forms aplikace (.NET)** šablona vytváří [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] aplikace Windows Forms. Další informace najdete v tématu [postupy: vytvoření projektu aplikace Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
 Ladění tento typ aplikace v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je podobná ve spravovaných aplikacích Windows Forms.  
  
 Při vytváření projektu Windows Forms pomocí šablony projektu, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky vytvoří požadované nastavení pro konfiguraci ladění a vydání. Pokud potřeby můžete změnit tato nastavení v  **\<název projektu > stránky vlastností** dialogové okno. Další informace najdete v tématu [konfigurace ladění a verzí](../debugger/how-to-set-debug-and-release-configurations.md).  
  
 Další informace najdete v tématu [nastavení projektu pro konfiguraci ladění C++](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
 Jiný způsob, jak ladit aplikaci Windows Forms, je-li spustit aplikaci mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a k němu připojí. Další informace najdete v tématu [připojení ke spuštění programu nebo více programů](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
 [V tomto tématu](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)  
  
## <a name="see-also"></a>Viz také  
 [Základy ladicího programu](../debugger/debugger-basics.md)   
 [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Připojení ke spuštění programu nebo více programů](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Konfigurace ladění a verzí](../debugger/how-to-set-debug-and-release-configurations.md)   
 [Postupy: vytvoření projektu aplikace Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)