---
title: Ladění projektů knihovny DLL | Dokumentace Microsoftu
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
ms.openlocfilehash: 04ffdd5d0256ae0fc42b89dfa850fb0ae2d36748
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49818663"
---
# <a name="debugging-dll-projects-from-visual-studio"></a>Ladění projektů knihovny DLL v sadě Visual Studio
Následující šablony sady Visual Studio vytvoří knihovny DLL:  
  
-   (C++, C# a Visual Basic) Knihovna tříd   

-   (C++): Projekt konzoly Win32 knihovny DLL
  
     Další informace najdete v tématu [techniky ladění MFC](../debugger/mfc-debugging-techniques.md).

-   (C++, C# a Visual Basic): Knihovna ovládacích prvků formulářů Windows
  
     Ladění knihovny ovládacích prvků formulářů Windows je podobné ladění projektu knihovny tříd. Ve většině případů budete volat ovládací prvek Windows z jiného projektu. Při ladění volajícího projektu můžete krokovat s vnořením kódu ovládacího prvku Windows, nastavit zarážky a provádět jiné operace ladění. Další informace najdete v tématu [ovládacích prvků Windows Forms](/dotnet/framework/winforms/controls/index).  

  
##  <a name="vxtskdebuggingdllprojectsbuildingadebugversion"></a> Sestavení ladicí verze  
 Bez ohledu na to, jak spouštíte ladění Ujistěte se, že nejprve sestavení ladicí verze knihovny DLL a ujistěte se, že ladicí verze je v umístění, kde se očekává, že aplikace ji najít. To se může zdát zřejmé, ale pokud zapomenete tento krok, aplikace může najít jinou verzi knihovny DLL a načíst ji. Program bude pokračovat spustit, zatímco se budete divit, proč vaší zarážky nikdy dosaženo. Když ladíte, můžete ověřit, které knihovny DLL váš program načetl, otevřením ladicího programu **moduly** okna. **Moduly** okno uvádí jednotlivé knihovny DLL nebo EXE načtené v procesu, který ladíte. Další informace najdete v tématu [postupy: použití okna moduly](../debugger/how-to-use-the-modules-window.md).  
 Aby ladicí program připojil kód napsaný v jazyce C++, musí kód generovat `DebuggableAttribute`. Můžete přidat to do kódu automaticky díky propojení s [/assemblydebug](/cpp/build/reference/assemblydebug-add-debuggableattribute) – možnost linkeru.  
  
##  <a name="vxtskdebuggingdllprojectsmixedmodedebugging"></a> Ladění ve smíšeném režimu  
 Volající aplikace, která volá vaši knihovnu DLL je možné psát v spravovaném kódu nebo nativním kódu. Pokud je vaše spravovaná knihovna DLL volána pomocí nativního kódu a chcete obojí ladit, spravované a nativní ladicí programy musí být povoleny. To můžete vybrat  **\<Projekt > stránky vlastností** nebo dialogovém okně. Postup závisí na tom, zda spustíte ladění z projektu knihovny DLL nebo projekt volající aplikace. Další informace najdete v tématu [postupy: ladění ve smíšeném režimu](../debugger/how-to-debug-in-mixed-mode.md).  
  
##  <a name="vxtskdebuggingdllprojectschangingdefaultconfigurations"></a> Změna výchozí konfigurace  
 Když vytvoříte projekt konzolové aplikace pomocí šablony projektu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky vytvoří požadované nastavení konfigurace Debug a Release. V případě potřeby můžete změnit tato nastavení. Další informace najdete v tématu [nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md), [nastavení projektu pro ladění konfigurace jazyka C#](../debugger/project-settings-for-csharp-debug-configurations.md), [nastavení projektu pro konfiguraci ladění jazyka Visual Basic ](../debugger/project-settings-for-a-visual-basic-debug-configuration.md), a [postupy: Konfigurace nastavení ladění a verzí](../debugger/how-to-set-debug-and-release-configurations.md).  
  
##  <a name="vxtskdebuggingdllprojectswaystodebugthedll"></a> Způsoby, jak ladit knihovnu DLL  
 Všechny projekty v této části vytvoří knihovnu DLL. Knihovnu DLL nelze spustit přímo. musí být volána aplikací, obvykle EXE. Další informace najdete v tématu [vytváření a správa projektů Visual C++](/cpp/ide/creating-and-managing-visual-cpp-projects). Volající aplikace mohou přizpůsobit některé z následujících kritérií:  
  
- Aplikace vytvořené v jiném projektu ve stejném [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení, které obsahuje knihovnu tříd.  
  
- Existující aplikace již nasazená v testovacím nebo produkčním počítači.  
  
- Nachází se na webu a přístup prostřednictvím adresy URL.  
  
- Webová aplikace, které obsahuje webovou stránku obsahující knihovnu DLL.  
  
###  <a name="vxtskdebuggingdllprojectsthecallingapplication"></a> Ladění volající aplikace  
Chcete-li ladit knihovnu DLL, začněte laděním volající aplikace, obvykle buď aplikace EXE nebo webová aplikace. Existuje několik způsobů, jak ho ladit.  
  
- Pokud máte projekt pro volající aplikace, můžete otevřít tento projekt a spustit provádění z **ladění** nabídky. Další informace najdete v tématu [Začínáme s ladicím programem](../debugger/getting-started-with-the-debugger.md).  
  
- Pokud volající aplikace existující program již nasazený v testovacím nebo produkčním počítači a je již spuštěna můžete připojit k němu. Tuto metodu použijte, pokud je knihovna DLL kontrolovaně aplikace Internet Explorer nebo ovládacího prvku na webové stránce. Další informace najdete v tématu [postupy: připojení k procesu spuštění](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
- Můžete ho ladit z projektu knihovny DLL. Další informace najdete v tématu [postupy: ladění z projektu knihovny DLL](../debugger/how-to-debug-from-a-dll-project.md).  
  
- Můžete ho ladit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] [podokna](#vxtskdebuggingdllprojectstheimmediatewindow). V takovém případě **okamžité** okno hraje roli aplikace.  
  
Před zahájením ladění volající aplikace je obvyklé nastavit zarážku v knihovně tříd. Další informace najdete v tématu [pomocí zarážek](../debugger/using-breakpoints.md). Při dosažení zarážky, můžete krokovat kód, sledování akce na každém řádku, dokud nebude problém. Další informace najdete v tématu [vyhledání kódu v ladicím programu](../debugger/navigating-through-code-with-the-debugger.md).
  
###  <a name="vxtskdebuggingdllprojectstheimmediatewindow"></a> Příkazové podokno  
 Bez nutnosti volání aplikace můžete vyhodnotit funkce nebo metody v knihovně DLL. Proveďte ladění v době návrhu a použít **okamžité** okna. Chcete-li ladit tímto způsobem, proveďte tyto kroky při otevřeném projektu knihovny DLL:  
  
1.  Spusťte ladicí program **okamžité** okna.  
  
2.  Chcete-li otestovat metodu s názvem `Test` ve třídě `Class1`, vytvoří instanci objektu typu `Class1` zadáním následujícího kódu jazyka C# do okna příkazy. Tento spravovaný kód funguje pro Visual Basic a C++ s příslušnými změnami syntaxe:  
  
    ```cpp
    Class1 obj = new Class1();  
    ```  
  
     V jazyce C# musí být všechny názvy plně kvalifikovaný. Kromě toho jakékoli metody nebo proměnné musí být v aktuálním měřítku a kontextu relace ladění.  
  
3.  Za předpokladu, že `Test` má jednu `int` parametr, vyhodnotit `Test` pomocí **okamžité** okno:  
  
    ```cpp
    ?obj.Test(10)  
    ```  
  
     Výsledek bude vytištěn v **okamžité** okna.  
  
4.  Můžete pokračovat v ladění `Test` umístěním zarážky dovnitř a opakovaným vyhodnocením funkce:  
  
    ```cpp
    ?obj.Test(10);  
    ```  
  
     Bude dosaženo zarážkou a budete moci krokovat `Test`. Poté, co provádění opustí `Test`, ladicí program bude zpět v návrhovém režimu.

## <a name="vxtskdebuggingdllprojectsexternal"></a> Ladění externí knihovny DLL z projektu C++

Pokud ladíte externí knihovny DLL do projektu, ladění funkce dostupné (jako je například krokování kódem) bude záviset na [konfiguraci ladění knihovny DLL](#vxtskdebuggingdllprojectsbuildingadebugversion) když byl sestaven a zda [soubor typu .pdb](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) a dalších požadovaných souborů pro knihovnu DLL jsou k dispozici.

Váš projekt musí být schopna najít knihovnu DLL a soubor PDB pro ladění. Můžete vytvořit vlastního sestavení úlohu kopírování těchto souborů do  **\<složky projektu > \Debug** výstupní složky, nebo můžete zkopírovat soubory do složky výstupu ručně.

Můžete snadno nastavit umístění souborů záhlaví a <em>soubory .lib na stránkách vlastností (klikněte pravým tlačítkem na projekt C++ a zvolte ** Zobrazit vlastnosti</em><em>a klikněte na tlačítko **všechny konfigurace</em>* ) bez nutnosti kopírovat do výstupní složky:

- Složka C/C++ (obecná kategorie) – zadejte složku obsahující soubory hlaviček v **další adresáře souborů k zahrnutí** pole.
- Složka linkeru (obecná kategorie) – zadejte složku, která obsahuje soubor .lib v **další adresáře knihoven** pole. 
- Složka linkeru (kategorie vstup) – zadejte úplnou cestu a název souboru pro soubor .lib v **Další závislosti** pole.

Pokud je konfigurace správná, můžete ladit pomocí spuštění ze **ladění** nabídky.

Další informace o nastavení projektu, naleznete v tématu [stránky vlastností (Visual C++)](/cpp/ide/property-pages-visual-cpp).
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Typy projektů Visual C++](../debugger/debugging-preparation-visual-cpp-project-types.md)   
 [C#, F # a typy projektů jazyka Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Nastavení projektu pro jazyk C# konfiguraci ladění](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Konfigurace ladění projektu v jazyce Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)
