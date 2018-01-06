---
title: "Postupy: ladění z projektu knihovny DLL | Microsoft Docs"
ms.custom: 
ms.date: 05/24/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- DLL projects, debugging
- debugging DLLs
- DLLs, debugging projects
- debugging [Visual Studio], DLLs
ms.assetid: 40a94339-d3f7-4ab9-b8a1-b8cf82942f44
caps.latest.revision: "30"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f50c41a18f6d018ca717fbfd0cd926da8e6dcf65
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-from-a-dll-project-in-visual-studio"></a>Postupy: ladění z projektu knihovny DLL v sadě Visual Studio
Jednou z možností ladění projektu knihovny DLL je zadání volající aplikace ve vlastnostech projektu projektu knihovny DLL a potom můžete spustit ladění z projektu knihovny DLL, sám sebe. Pro tuto metodu za účelem práce, aplikace musí volat knihovnu DLL a knihovny DLL musí být v umístění, kde se předpokládá, že aplikace bude (jinak, aplikace může najít jinou verzi knihovny DLL a načíst, namísto toho a ho nebude stiskněte váš zarážky). Dalším metodám ladění knihoven DLL, najdete v části [ladění projektů knihovny DLL](../debugger/debugging-dll-projects.md).
  
Pokud spravovaná knihovna DLL je volána metodou nativního kódu a chcete ladit obě, můžete toto určíte ve vlastnostech projektu. Další informace najdete v tématu [postupy: ladění ve smíšeném režimu](../debugger/how-to-debug-in-mixed-mode.md).   

Stránky vlastností C++ se liší v rozložení a obsah z jazyka C# a Visual Basic – stránky vlastností. 
  
### <a name="to-specify-the-calling-application-in-a-c-project"></a>Chcete-li určit volající aplikace v projektu jazyka C++  
  
1.  Klikněte pravým tlačítkem na uzel projektu v **Průzkumníku řešení** a vyberte **vlastnosti**.  
  
2.  Ujistěte se, že **konfigurace** pole v horní části okna je nastaveno **ladění**. 

    A **ladění** konfigurace je nutná pro tuto metodu. 
  
3.  Přejděte na **vlastnosti konfigurace > ladění**.  
  
4.  V **ladicí program ke spuštění** vyberte **místní ladicí program Windows** nebo **vzdáleného ladicího programu Windows**.  
  
5.  V **příkaz** nebo **vzdáleného příkazu** pole, přidejte název plně kvalifikovanou cestu volající aplikace (například soubor s příponou .exe).

    ![Ladění vlastnosti – okno](../debugger/media/dbg-debugging-properties-dll.png "DebuggingPropertiesWindow")  
  
6.  Přidat všechny potřebné program argumenty pro **argumenty příkazu** pole.  
  
### <a name="to-specify-the-calling-application-in-a-c-or-visual-basic-project"></a>Pokud chcete zadat volající aplikace do projektu C# nebo Visual Basic  
  
1.  Klikněte pravým tlačítkem na uzel projektu v **Průzkumníku řešení** a vyberte **vlastnosti**a pak vyberte **ladění** kartě.

2.  Ujistěte se, že **konfigurace** pole v horní části okna je nastaveno **ladění**.

3.  (Rozhraní .NET framework) Vyberte **počáteční vnějšímu programu**a přidejte název plně kvalifikovanou cestu volající aplikace.

4.  (.NET core) Vyberte **spustitelný soubor** z **spusťte** seznamu a poté přidejte název volající aplikace ve plně kvalifikovanou cestu **spustitelný soubor** pole. 
  
     Pokud potřebujete přidat argumenty příkazového řádku externí program, přidejte je do **argumenty příkazového řádku** (nebo **aplikace argumenty**) pole.

    ![Ladění vlastnosti – okno](../debugger/media/dbg-debugging-properties-dll-csharp.png "DebuggingPropertiesWindow") 

5.  Pokud potřebujete, můžete také volat aplikace jako adresu URL. (Můžete chtít provést v případě, že ladíte spravovanou knihovnu DLL používá místní aplikace ASP.NET.)  
  
     V části **spustit akci**, vyberte **spuštění prohlížeče s adresou URL:** přepínač a zadejte adresu URL.
  
### <a name="to-start-debugging-from-the-dll-project"></a>Spustit ladění z projektu knihovny DLL  
  
1.  Nastavte zarážky v projektu knihovny DLL. 

2.  Klikněte pravým tlačítkem na projekt knihovny DLL a zvolte **nastavit jako spouštěný projekt**. 

    (Také, ujistěte se, že **konfigurace řešení** je stále nastaveno na **ladění**.)   
  
3.  Spuštění ladění (stiskněte klávesu F5, klikněte na zelenou šipku nebo klikněte na tlačítko **ladění > Spustit ladění**).

    V knihovně DLL, se setkají zarážky. Pokud nejste možnost zadat zarážce, ujistěte se, zda vaše knihovna DLL výstup (ve výchozím nastavení, **project\Debug** složky) je v umístění, že očekává, že je volající aplikace k vyhledání.
  
## <a name="see-also"></a>Viz také  
 [Ladění projektů knihovny DLL](../debugger/debugging-dll-projects.md)   
 [Konfigurace ladění nastavení projektu pro jazyk C#](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Nastavení projektu jazyka Visual Basic konfiguraci ladění](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)