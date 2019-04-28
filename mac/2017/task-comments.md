---
title: Komentáře k úkolům
description: Přidání komentáře k úkolu do kódu
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 562DCB46-D8FA-4DC4-AAEA-F274448C4CD2
ms.openlocfilehash: 3caef73ba46afd8eaf90826540248cb2d5c4efef
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62987070"
---
# <a name="task-comments"></a>Komentáře k úkolům

Při psaní kódu, se standardním postupem chcete explicitně přidat komentář nedokončené nebo problematického kódu a rychlé řešení s upozorněními. Tokeny signál výchozí poskytovaný sadou Visual Studio for Mac jsou TODO, HACK, FIXME a VRÁCENO. Individuální tokeny lze definovat v rámci **sady Visual Studio > Předvolby > prostředí > úlohy**, jak je znázorněno na následujícím obrázku:

![Předvolby seznamu úkolů](media/source-editor-image10.png)

Chcete-li přidat nový komentář k úkolu, přidejte komentář, který obsahuje klíčové slovo úloh. Příklad:

```csharp
//TODO: Finish this for all properties.
```

Visual Studio pro Mac zdůrazňující tyto značky zvýrazněním v **seznamu úkolů** panel, který je možné zobrazit tak, že přejdete do **zobrazení > panely > úlohy**:

![Panel seznamu úloh](media/source-editor-image11.png)

## <a name="see-also"></a>Viz také:

- [Pomocí seznamu úkolů (Visual Studio na Windows)](/visualstudio/ide/using-the-task-list)