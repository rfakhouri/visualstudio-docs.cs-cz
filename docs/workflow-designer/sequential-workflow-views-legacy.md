---
title: Návrhář postupu provádění - sekvenční pracovní postup zobrazení (zastaralé)
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- sequential workflow views
- sequential workflows, views
ms.assetid: 135f24b9-1b37-442b-9ef8-f0f2108a3212
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ce1217ea629ae0301b72b444161d61db4fe448b1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="sequential-workflow-views-legacy"></a>Sekvenční pracovní postup zobrazení (zastaralé)

Visual Studio 2010 zajišťuje starší verze Návrháře pracovního postupu systému Windows, které je možné cílit na rozhraní .NET Framework verze 3.5 nebo WinFX.

Návrhář postupu provádění poskytuje způsob, jak graficky vytvářet aplikace Windows Workflow Foundation (WF) pomocí uživatelského rozhraní známé Visual Studio. Aplikace Windows Workflow Foundation (WF) se skládají z kroků procesu pracovního postupu nazývají aktivity. Pokud chcete vytvořit pracovní postup, tvoří aktivity na návrhovou plochu přetažením návrháře jejich odpovídajících aktivit z **sada nástrojů** na návrhovou plochu.

Při vytváření sekvenční pracovní postup, který je [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040), jsou k dispozici tři zobrazení pracovního postupu. Tato zobrazení jsou k dispozici **pracovního postupu** nabídky a v místní nabídce na návrhovou plochu.

Následující tabulka uvádí název a popis jednotlivých zobrazení.

|Možnost nabídky nebo karty|Popis|
|----------------------|-----------------|
|**Zobrazení sekvenčního pracovního postupu**|Klikněte pravým tlačítkem na návrhové plochy a vyberte možnost **sekvenčního pracovního postupu zobrazení** možnosti v místní nabídce se zobrazí **sekvenční pracovní postup** zobrazení, které zobrazuje podle činností grafického rozhraní reprezentace sekvenčního pracovního postupu. Nebo vyberte **sekvenčního pracovního postupu zobrazení** z **pracovního postupu** nabídky.|
|**Obslužná rutina zrušit zobrazení**|Klikněte pravým tlačítkem na návrhové plochy a vyberte možnost **obslužná rutina zrušit zobrazení** možnosti v místní nabídce se zobrazí **sekvenční pracovní postup** zobrazení, která ukazuje [CancellationHandlerActivity ](http://go.microsoft.com/fwlink?LinkID=65050) aktivity související s pracovním postupem. Nebo vyberte **obslužná rutina zrušit zobrazení** z **pracovního postupu** nabídky.|
|**Obslužná rutina chyb zobrazení**|Klikněte pravým tlačítkem na návrhové plochy a vyberte možnost **obslužná rutina chyb zobrazení** možnosti v místní nabídce se zobrazí **chyb** zobrazení, která ukazuje [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) aktivity související s pracovním postupem. Nebo vyberte **obslužná rutina chyb zobrazení** z **pracovního postupu** nabídky.|

 Další informace o podobné zobrazení najdete v tématu [zobrazení aktivity (zastaralé)](../workflow-designer/activity-views-legacy.md).

## <a name="see-also"></a>Viz také

- [Zobrazení aktivit (starší verze)](../workflow-designer/activity-views-legacy.md)
- [Vytváření projektů pracovních postupů starších verzí](../workflow-designer/creating-legacy-workflow-projects.md)
- [Pracovní postup pro vytváření obsahu režimy](http://go.microsoft.com/fwlink?LinkID=65014)