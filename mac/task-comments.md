---
title: Komentáře k úkolům
description: Přidání komentáře k úkolu do kódu
author: cobey
ms.author: cobey
ms.date: 05/06/2018
ms.assetid: 562DCB46-D8FA-4DC4-AAEA-F274448C4CD2
ms.openlocfilehash: d88b74ab953f97e061f4be3befc227646006f38b
ms.sourcegitcommit: 7fbfb2a1d43ce72545096c635df2b04496b0be71
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/09/2019
ms.locfileid: "67692314"
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