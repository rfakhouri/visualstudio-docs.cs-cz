---
title: "Spuštění aplikace UWP v místním počítači | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
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
ms.assetid: e42a21a8-6423-4caf-b4dc-72b263e76019
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 08e0108a3fb7a93dc19fe1aa96988912068ace70
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="run-uwp-apps-on-the-local-machine"></a>Spuštění aplikace UWP v místním počítači
![Platí pouze pro Windows](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Ladění, testování nebo spuštění analýzu výkonu na aplikace pro UPW, můžete spustit aplikace na stejném počítači který je hostitelem Visual Studio. Pokud zobrazení na zařízení dotykovým ovládáním, mohou vykonávat všechny funkce aplikace; jinak bude omezeno na gesta myši a klávesnice.  
  
##  <a name="BKMK_How_to_run_on_a_local_machine"></a>Jak spustit v místním počítači  
 Chcete-li spustit aplikace v místním počítači, vyberte **místního počítače** z rozevíracího seznamu vedle tlačítko Spustit ladění ladicí program **standardní** panelu nástrojů.  
  
 ![Spustit v místním počítači](../debugger/media/vsrun_f5_local.png "VSRUN_F5_Local")  
  
 Pokud nevidíte **standardní** nástrojů, klikněte na tlačítko **zobrazení** nabídky, přejděte na příkaz **panely nástrojů**a potom klikněte na **standardní**.  
  
 Výběr provedený v rozevíracím seznamu je uchován v souboru projektu vlastnosti a změní výchozí spustit cíl.  
  
 Spuštění cílového můžete vytvořit také přímo v souboru vlastnosti projektu. Klikněte pravým tlačítkem myši na název projektu v **Průzkumníku řešení** a potom zvolte **vlastnosti**. Udělejte jednu z následujících akcí:  
  
-   V projektech pro C# a Visual Basic, klikněte na tlačítko **ladění** a pak vyberte **místního počítače** z **cílové zařízení** rozevíracího seznamu.  
  
     ![C &#35; a stránce vlastností projektu jazyka Visual Basic](../debugger/media/vsrun_cs_vb_projprop_local.png "VSRUN_CS_VB_ProjProp_Local")  
  
-   V projektech C++ a JavaScript, rozbalte **vlastnosti konfigurace** uzel, klikněte na tlačítko **ladění**a potom vyberte **místní ladicí program** z **ladicí program ke spuštění** seznamu.  
  
     ![C & č. 43; & č. 43; Stránka vlastností projektu jazyka JavaScript a](../debugger/media/vsrun_cpp_js_projprop_local.png "VSRUN_CPP_JS_ProjProp_Local")  