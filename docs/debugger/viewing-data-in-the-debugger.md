---
title: Vytváření vlastních zobrazení dat v ladicím programu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 06/27/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], inspecting programs
- debugger, viewing data
ms.assetid: 13e1105f-f987-402e-9108-ec6ac12be042
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02bb65aa2b0601315a3f5dec2cc9459af210db3e
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39177669"
---
# <a name="create-custom-views-of-data-in-the-visual-studio-debugger"></a>Vytváření vlastních zobrazení dat v ladicím programu sady Visual Studio
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Ladicí program poskytuje celou řadu nástrojů pro prohlížení a úpravy stavu programu. Většina těchto nástrojů funguje pouze v režimu pozastavení.

## <a name="create-custom-views-of-data-in-variable-windows-and-datatips"></a>Vytváření vlastních zobrazení dat v oknech proměnných a datové tipy
 Mnoho [ladicího programu systému windows](../debugger/debugger-windows.md), například **automatické hodnoty** a **Watch** windows, můžete kontrolovat proměnné při ladění. Můžete přizpůsobit zobrazení typů nativní a spravované objekty v oknech proměnných ladicího programu a [DataTips](../debugger/view-data-values-in-data-tips-in-the-code-editor.md). To může být užitečné, chcete-li zobrazit typy, které vytvoříte ve svých vlastních aplikacích. Další informace najdete v tématu [vytváření vlastních zobrazení nativních objektů](../debugger/create-custom-views-of-native-objects.md) a [vytváření vlastních zobrazení spravovaných objektů](../debugger/create-custom-views-of-dot-managed-objects.md).
  
## <a name="create-custom-visualizers"></a>Vytváření vlastních vizualizérů  
 Vizualizéry umožňují zobrazení obsahu objektu nebo proměnné srozumitelným způsobem. V ladicím programu sady Visual Studio vizualizéru odkazuje na jiný windows, které můžete otevřít pomocí ikony lupy ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Vizualizéru ikonu"). Například můžete použít HTML visualizer zobrazení jako řetězec HTML, jako by byl interpretován a zobrazen v prohlížeči. K vizualizátorům můžete přistupovat z datových typů, **Watch** okně **automatické hodnoty** okně **místní hodnoty** okno, nebo **QuickWatch** dialogové okno pole. Další informace najdete v tématu [vytváření vlastních vizualizérů](../debugger/create-custom-visualizers-of-data.md).
  
## <a name="see-also"></a>Viz také  
 [Základy ladicího programu](../debugger/getting-started-with-the-debugger.md)   
 [Okno příkazového řádku](../ide/reference/command-window.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)