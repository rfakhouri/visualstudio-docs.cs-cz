---
title: Vytvořit vlastní zobrazení dat v ladicím programu | Microsoft Docs
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
ms.openlocfilehash: 5ccf8b24618aeb2cb4b8774786bf96b2184f5da9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31482175"
---
# <a name="create-custom-views-of-data-in-the-visual-studio-debugger"></a>Vytvořit vlastní zobrazení dat v ladicím programu sady Visual Studio
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Ladicí program poskytuje celou řadu nástrojů pro kontroly a úprava stavu vašeho programu. Většina těchto nástrojů funkce pouze v režimu pozastavení.

## <a name="create-custom-views-of-data-in-variable-windows-and-datatips"></a>Vytvořit vlastní zobrazení dat ve windows proměnné a datatips –
 Řadu [ladicího programu windows](../debugger/debugger-windows.md), například **automobily** a **sledovat** windows, umožňují zkoumat proměnné při ladění. Můžete přizpůsobit zobrazení typů nativní a spravované objekty v proměnnými ladicího programu a v [datatips –](../debugger/view-data-values-in-data-tips-in-the-code-editor.md). To může být užitečné k zobrazení typy, které vytvoříte v aplikaci. Další informace najdete v tématu [vytváření vlastních pohledů nativních objektů](../debugger/create-custom-views-of-native-objects.md) a [vytvářet vlastní zobrazení spravovaných objektů](../debugger/create-custom-views-of-dot-managed-objects.md).
  
## <a name="create-custom-visualizers"></a>Vytvořit vlastní vizualizérech  
 Vizualizérech umožňují zobrazit obsah objektu nebo proměnná smysluplný způsobem. V ladicím programu sady Visual Studio, vizualizéru odkazuje na jiný windows, které můžete otevřít pomocí ikonu lupy ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "vizualizér ikonu"). Například můžete vizualizér HTML zobrazíte řetězec HTML, jako by být interpretovat a zobrazí v prohlížeči. Vizualizérech můžete přistupovat z datatips –, **sledovat** okně **automobily** okně **místní hodnoty –** okno, nebo **QuickWatch** dialogové okno pole. Další informace najdete v tématu [vytvořit vlastní vizualizérech](../debugger/create-custom-visualizers-of-data.md).
  
## <a name="see-also"></a>Viz také  
 [Základy ladicího programu](../debugger/debugger-basics.md)   
 [Příkazové okno](../ide/reference/command-window.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)