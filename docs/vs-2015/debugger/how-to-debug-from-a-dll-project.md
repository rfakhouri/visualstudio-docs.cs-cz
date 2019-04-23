---
title: 'Postupy: Ladění z projektu knihovny DLL | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- DLL projects, debugging
- debugging DLLs
- DLLs, debugging projects
- debugging [Visual Studio], DLLs
ms.assetid: 40a94339-d3f7-4ab9-b8a1-b8cf82942f44
caps.latest.revision: 33
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 360384118f5c2d02801b63b8836800eca5e26d78
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60102247"
---
# <a name="how-to-debug-from-a-dll-project"></a>Postupy: Ladění z projektu knihovny DLL
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Chcete-li spustit ladění projektu knihovny DLL, musíte zadat volající aplikace ve vlastnostech projektu. Stránky vlastností C++ se liší v rozložení a obsah z jazyka C# a Visual Basic – stránky vlastností.  
  
 Pokud je spravovaná knihovna DLL volána pomocí nativního kódu a chcete obojí ladit, můžete toto určíte ve vlastnostech projektu. Další informace najdete v tématu [jak: Ladění ve smíšeném režimu](../debugger/how-to-debug-in-mixed-mode.md).  
  
> [!NOTE]
>  V edicích Express sady Visual Studio nelze zadat externí volající aplikace. Místo toho potřebujete přidat spustitelný projekt do řešení, nastavte jako spouštěný projekt a volat metody v knihovně DLL z spustitelný projekt.  
  
### <a name="to-specify-the-calling-application-in-a-c-project"></a>Chcete-li určit volající aplikace v projektu jazyka C++  
  
1. Klikněte pravým tlačítkem na uzel projektu v **Průzkumníka řešení** a vyberte **vlastnosti**. Přejděte **ladění** kartu.  
  
2. Ujistěte se, že **konfigurace** pole v horní části okna je nastaveno **ladění**.  
  
3. Přejděte na **konfigurační vlastnosti / ladění**.  
  
4. V **ladicí program ke spuštění** klikněte na položku **místní ladicí program Windows** nebo **vzdálený ladicí program Windows**.  
  
5. V **příkaz** nebo **vzdálený příkaz** přidejte název plně kvalifikované cesty aplikace.  
  
6. Přidat všechny argumenty potřebné program **argumenty příkazu** pole.  
  
### <a name="to-specify-the-calling-application-in-a-c-or-visual-basic-project"></a>Pokud chcete zadat volající aplikace do projektu C# nebo Visual Basic  
  
1. Klikněte pravým tlačítkem na uzel projektu v **Průzkumníka řešení** a vyberte **vlastnosti**. Přejděte **ladění** kartu.  
  
     Vyberte **externí program Start**a přidejte název plně kvalifikované cesty ke spuštění programu.  
  
     Pokud je potřeba přidat externí program argumenty příkazového řádku, přidejte je **argumenty příkazového řádku** pole.  
  
2. Můžete také volat aplikace jako adresa URL. (Můžete to provést, pokud ladíte spravovaný knihovnu DLL používá místní aplikace ASP.NET.)  
  
     V části **spustit akci**, vyberte **spuštění prohlížeče v adrese URL:** přepínač a zadejte adresu URL.  
  
### <a name="to-start-debugging-from-the-dll-project"></a>Pro spuštění ladění z projektu knihovny DLL  
  
1. Podle potřeby nastavit zarážky.  
  
2. Spustit ladění (stisknutím klávesy F5, klikněte na zelenou šipku nebo klikněte na tlačítko **ladění / spuštění ladění**).  
  
## <a name="see-also"></a>Viz také  
 [Ladění projektů knihovny DLL](../debugger/debugging-dll-projects.md)   
 [Nastavení projektu pro jazyk C# konfiguraci ladění](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Konfigurace ladění projektu v jazyce Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)
