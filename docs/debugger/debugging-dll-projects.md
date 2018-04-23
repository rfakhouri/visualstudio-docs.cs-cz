---
title: Ladění projektů knihovny DLL | Microsoft Docs
ms.custom: ''
ms.date: 05/23/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging DLLs
- templates, debugging DLLs
- DLLs, debugging
- debugging [Visual Studio], DLLs
ms.assetid: 433cab30-d191-460b-96f7-90d2530ca243
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c5da503dd3eb1aec83c5f1fdef58261960d66d7
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="debugging-dll-projects-from-visual-studio"></a>Ladění projektů knihovny DLL ze sady Visual Studio
Následující šablony sady Visual Studio vytvořte knihovny DLL:  
  
-   (C++, C# a Visual Basic) Knihovna tříd   

-   (C++): projektu knihovny DLL konzoly Win32
  
     Další informace najdete v tématu [techniky ladění MFC](../debugger/mfc-debugging-techniques.md).

-   (C++, C# a Visual Basic): Knihovna ovládací prvek Windows Forms
  
     Ladění knihovnu ovládacích prvků Windows Forms je podobná ladění projektu knihovny tříd. Ve většině případů bude volat ovládacího prvku Windows z jiného projektu. Při ladění projektu pro volání, kroku do kódu ovládacího prvku systému Windows, nastavit zarážky a provádění dalších operací ladění. Další informace najdete v tématu [ovládacích prvků Windows Forms](/dotnet/framework/winforms/controls/index).  

  
##  <a name="vxtskdebuggingdllprojectsbuildingadebugversion"></a> Sestavení ladicí verze  
 Bez ohledu na to, jak spustit ladění Ujistěte se, nejprve sestavení ladicí verze knihovny DLL a ujistěte se, že ladicí verze je v umístění, kde se předpokládá, že aplikace ji najít. Toto se může zdát zřejmé, ale pokud zapomenete tento krok, může aplikace najít jinou verzi knihovny DLL a načíst. Program pak bude spuštěna, zatímco vás zajímat, proč byl vaší zarážce nikdy vybrán. Při ladění, můžete ověřit, které knihovny DLL vašeho programu načetl otevřením ladicího programu **moduly** okno. **Moduly** okno uvádí každý DLL nebo EXE načíst v procesu, kterou ladíte. Další informace najdete v tématu [postupy: použití okna moduly](../debugger/how-to-use-the-modules-window.md).  
 V ladicím programu pro připojení k kód napsaný v jazyce C++, musí emitování kód `DebuggableAttribute`. Můžete přidat to kódu automaticky pomocí propojení s [/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute) – možnost linkeru.  
  
##  <a name="vxtskdebuggingdllprojectsmixedmodedebugging"></a> Ladění ve smíšeném režimu  
 Volající aplikace, která volá knihovny DLL lze zapsat ve spravovaném kódu nebo nativního kódu. Pokud vaše spravovaná knihovna DLL je volána metodou nativního kódu a chcete ladit obě, spravovaná a nativní ladicí programy obě povoleny. Můžete vybrat v  **\<Projekt > stránky vlastností** nebo dialogovém okně. Tento postup závisí na tom, jestli spuštění ladění z projektu knihovny DLL nebo volání projekt aplikace. Další informace najdete v tématu [postupy: ladění ve smíšeném režimu](../debugger/how-to-debug-in-mixed-mode.md).  
  
##  <a name="vxtskdebuggingdllprojectschangingdefaultconfigurations"></a> Změna výchozí konfigurace  
 Při vytváření projektu konzolové aplikace pomocí šablony projektu, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky vytvoří požadované nastavení pro konfiguraci ladění a vydání. V případě potřeby můžete změnit tato nastavení. Další informace najdete v tématu [nastavení projektu pro konfiguraci ladění C++](../debugger/project-settings-for-a-cpp-debug-configuration.md), [nastavení projektu pro ladění konfigurace C#](../debugger/project-settings-for-csharp-debug-configurations.md), [nastavení projektu pro konfiguraci ladění jazyka Visual Basic ](../debugger/project-settings-for-a-visual-basic-debug-configuration.md), a [postupy: Konfigurace sady ladění a verzí](../debugger/how-to-set-debug-and-release-configurations.md).  
  
##  <a name="vxtskdebuggingdllprojectswaystodebugthedll"></a> Způsoby, jak ladit knihovny DLL  
 Všechny projekty v této části vytvoří knihovnu DLL. Nelze spustit knihovnu DLL přímo; musí být voláno aplikací, obvykle EXE. Další informace najdete v tématu [vytváření a správa projekty Visual C++](/cpp/ide/creating-and-managing-visual-cpp-projects). Volající aplikace může podle některého z následujících kritérií:  
  
-   Aplikace vytvořené v jiném projektu ve stejné [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení, které obsahuje knihovnu tříd.  
  
-   Stávající aplikace nasazené na počítači testovací nebo produkčního prostředí.  
  
-   Umístěné na webu a přístupných prostřednictvím adresy URL.  
  
-   Webové aplikace, které obsahuje webové stránky, která vloží knihovnu DLL.  
  
###  <a name="vxtskdebuggingdllprojectsthecallingapplication"></a> Ladění volající aplikace  
Chcete-li ladit knihovny DLL, spusťte ladění volající aplikace, obvykle buď EXE nebo webovou aplikaci. Existuje několik způsobů k ladění ho.  
  
-   Pokud máte projekt pro volající aplikace, můžete otevřít daného projektu a spusťte provádění z **ladění** nabídky. Další informace najdete v tématu [Začínáme s ladicím programem](../debugger/getting-started-with-the-debugger.md).  
  
-   Pokud je volající aplikace je program pro existující nasazené v testu nebo produkčním počítači a je již spuštěna můžete připojit k němu. Tuto metodu použijte, pokud knihovnu DLL je hostitelem aplikace Internet Explorer ovládací prvek nebo ovládacího prvku na webové stránce. Další informace najdete v tématu [postupy: připojení ke spuštění procesu](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
-   Můžete ho ladění z projektu knihovny DLL. Další informace najdete v tématu [postupy: ladění z projektu knihovny DLL](../debugger/how-to-debug-from-a-dll-project.md).  
  
-   Můžete ladit z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] [hodnot proměnných](#vxtskdebuggingdllprojectstheimmediatewindow). V takovém případě **Immediate** okno hraje roli aplikace.  
  
Než začnete ladění volající aplikace, obvykle můžete nastavit zarážky v knihovně tříd. Další informace najdete v tématu [pomocí zarážek](../debugger/using-breakpoints.md). Když je průchodu zarážkou, můžete krokovat kód, sledování akce na každém řádku až izolovat daný problém. Další informace najdete v tématu [přejděte kódu v ladicím programu](../debugger/navigating-through-code-with-the-debugger.md).
  
###  <a name="vxtskdebuggingdllprojectstheimmediatewindow"></a> Příkazové podokno  
 Funkce nebo metody v knihovně DLL můžete vyhodnotit bez nutnosti volající aplikace. Proveďte ladění v době návrhu a použít **Immediate** okno. Chcete-li ladit tímto způsobem, proveďte tyto kroky při projektu knihovny DLL těchto kroků je otevřený:  
  
1.  Otevřete ladicího programu **Immediate** okno.  
  
2.  K testování metodu s názvem `Test` ve třídě `Class1`, vytvoří instanci objektu typu `Class1` zadáním následujícího kódu C# do hodnot proměnných. Tento spravovaný kód funguje pro Visual Basic a jazyce C++ pomocí vhodné syntaxe změny:  
  
    ```  
    Class1 obj = new Class1();  
    ```  
  
     Všechny názvy v jazyce C#, musí být plně kvalifikovaný. Kromě toho jakékoliv metody nebo proměnné musí být v aktuálním oboru a kontextu relaci ladění.  
  
3.  Za předpokladu, že `Test` má jednu `int` parametr vyhodnotit `Test` pomocí **Immediate** okno:  
  
    ```  
    ?obj.Test(10)  
    ```  
  
     Výsledek vytiskne **Immediate** okno.  
  
4.  Můžete pokračovat v ladění `Test` umístěním zarážku uvnitř ho a pak znovu vyhodnocení funkce:  
  
    ```  
    ?obj.Test(10);  
    ```  
  
     Bude dosaženo zarážce a bude moct jednotlivé kroky `Test`. Po spuštění opustil `Test`, ladicího programu bude zpátky v režimu návrhu.

## <a name="vxtskdebuggingdllprojectsexternal"></a> Ladění externí knihovny DLL z projektu jazyka C++

Pokud ladíte externí knihovny DLL do projektu, k dispozici (například procházení kódu) funkce ladění bude záviset na [konfiguraci ladění knihovny DLL](#vxtskdebuggingdllprojectsbuildingadebugversion) při byla vytvořena a zda [soubor .pdb](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) a dalších požadovaných souborů pro knihovnu DLL, které jsou k dispozici.

Projekt musí být schopni najít knihovnu DLL a souboru PDB slouží k ladění. Můžete vytvořit vlastní sestavovací úlohy kopírování těchto souborů do  **\<složky projektu > \Debug** výstupní složky, nebo můžete zkopírovat soubory do výstupní složky ručně.

Můžete snadno nastavit umístění *.lib soubory a soubory hlaviček na stránkách vlastností (pravým tlačítkem na projekt C++ a zvolte **zobrazit vlastnosti**a potom zvolte **všechny konfigurace**) bez nutnosti kopírování je do výstupní složky:

- Složka C/C++ (obecné kategorie) – zadejte složku obsahující soubory hlaviček v **další adresáře Include** pole.
- Složka linkeru (obecné kategorie) – zadejte ve složce obsahující soubor .lib v **další adresáře knihovny** pole. 
- Složka linkeru (kategorie vstup) – zadejte úplnou cestu a název souboru pro soubor .lib v **Další závislosti** pole.

Pokud je konfigurace správná, můžete ladit spuštěním provádění z **ladění** nabídky.

Další informace o nastavení projektu najdete v tématu [stránky vlastností (Visual C++)](/cpp/ide/property-pages-visual-cpp).
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Typy projektů Visual C++](../debugger/debugging-preparation-visual-cpp-project-types.md)   
 [C#, F # a typy projektů jazyka Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Konfigurace ladění nastavení projektu pro jazyk C#](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Nastavení projektu jazyka Visual Basic konfiguraci ladění](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)