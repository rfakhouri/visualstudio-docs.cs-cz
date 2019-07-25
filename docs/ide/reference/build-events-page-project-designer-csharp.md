---
title: Stránka Události sestavení, návrhář projektu (C#)
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- Project Designer, Build Events page
- pre-build events
- post-build events
ms.assetid: 3fff9ae5-213c-46ea-a660-1d70acb6c922
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ba429c116d44a5d79d935fe3a1ad07b6d5f36f79
ms.sourcegitcommit: 85d66dc9fea3fa49018263064876b15aeb6f9584
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2019
ms.locfileid: "68461842"
---
# <a name="build-events-page-project-designer-c"></a>Stránka Události sestavení, návrhář projektu (C#)

Pomocí stránky **události sestavení** **Návrháře projektu** můžete zadat pokyny ke konfiguraci sestavení. Můžete také zadat podmínky, za kterých budou spouštěny události po sestavení. Další informace najdete v tématu [jak: Zadejte události sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md)a [postupy: Zadejte události sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

**Konfigurace**

Tento ovládací prvek není na této stránce možné upravovat. Popis tohoto ovládacího prvku naleznete v tématu [Stránka sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).

**Platformy**

Tento ovládací prvek není na této stránce možné upravovat. Popis tohoto ovládacího prvku naleznete v tématu [Stránka sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).

**Příkazový řádek události před sestavením**

Určuje, které příkazy se mají provést před zahájením sestavení. Chcete-li zadat dlouhé příkazy, klikněte na tlačítko **Upravit před sestavením** a zobrazte tak [dialogové okno Příkazový řádek události před sestavením/po sestavení](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).

> [!NOTE]
> Události před sestavením se nespustí, pokud je projekt aktuální a není spuštěno žádné sestavení.

**Příkazový řádek události po sestavení**

Určuje všechny příkazy, které mají být provedeny po ukončení sestavení. Chcete-li zadat dlouhé příkazy, klikněte na **Upravit po sestavení** , aby se zobrazilo **dialogové okno Příkazový řádek události před sestavením/po sestavení**.

> [!NOTE]
> `call` Přidejte příkaz před všechny příkazy po sestavení, které spouštějí soubory. bat. Například `call C:\MyFile.bat` nebo `call C:\MyFile.bat call C:\MyFile2.bat`.

**Spustit událost po sestavení**

Určuje následující podmínky pro spuštění události po sestavení, jak je znázorněno v následující tabulce.

|Možnost|Výsledek|
|------------|------------|
|**Vždy**|Událost po sestavení se spustí bez ohledu na to, jestli je sestavení úspěšné.|
|**Po úspěšném sestavení**|Událost po sestavení se spustí, pokud je sestavení úspěšné. Proto se událost spustí i pro projekt, který je aktuální, pokud je sestavení úspěšné.|
|**Když sestavení aktualizuje výstup projektu**|Událost po sestavení se spustí pouze v případě, že výstupní soubor kompilátoru (. exe nebo. dll) je jiný než předchozí výstupní soubor kompilátoru. Proto se událost po sestavení nespustí, pokud je projekt aktuální.|

## <a name="see-also"></a>Viz také:

- [Postupy: Určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)
- [Postupy: Určení událostí sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md)
- [Referenční dokumentace k vlastnostem projektu](../../ide/reference/project-properties-reference.md)
- [Kompilace a sestavení](../../ide/compiling-and-building-in-visual-studio.md)