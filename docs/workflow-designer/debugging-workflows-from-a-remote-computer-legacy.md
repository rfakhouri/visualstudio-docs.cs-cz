---
title: Návrhář postupu provádění – ladění pracovních ze vzdáleného počítače (zastaralé)
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, debugging remotely
- debugging workflows, remotely
- remote debugging, workflows
- debugging, remote
ms.assetid: 44eaec8f-9959-4ae7-a374-670946f933c1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 391180cd76fe5e0cccca802ba1cbfb78277dabc1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31967905"
---
# <a name="debugging-workflows-from-a-remote-computer-legacy"></a>Ladění pracovních ze vzdáleného počítače (zastaralé)

Toto téma popisuje postup ladění vzdálené starší verzi aplikace Windows Workflow Foundation (WF), které jsou vytvořeny pomocí návrháře pracovních postupů starší verze systému Windows. Pokud aplikace potřebuje cílit na rozhraní .NET Framework verze 3.5 nebo WinFX, používejte starší verzi návrháře pracovních postupů.

 Při instalaci sady Visual Studio, jednu z možností instalace součástí je instalace Visual Studio ladicí program pro Windows Workflow Foundation (WF). Tím se nainstaluje komponenty vzdáleného ladění. Tyto komponenty vzdáleného ladění musí být nainstalován v počítači, který cílení pro vzdálené pracovní postup ladění.

 Kromě toho je sestavení obsahující definice pracovního postupu starší verze pracovního postupu, který ladíte ve vzdáleném počítači musí být nainstalován v globální mezipaměti sestavení (GAC) z místního počítače, který se ladění z. Například pokud je starší verze pracovní postup spuštěný ve vzdáleném počítači A a ladíte z místního počítače B, definice pracovního postupu musí existovat v mezipaměti GAC počítače B. To umožňuje návrháře k deserializaci a zobrazení v počítači B značka pracovního postupu pracovního postupu, který běží na počítači A. vzdáleně Další informace o globální mezipaměti sestavení najdete v knihovně MSDN.

 Vzdálené ladění modelu Windows Workflow Foundation funguje stejně jako vzdálené ladění pro jiné komponenty sady Visual Studio. Další informace najdete v tématu Visual Studio vzdálené ladění v knihovně MSDN.

## <a name="see-also"></a>Viz také

- [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)