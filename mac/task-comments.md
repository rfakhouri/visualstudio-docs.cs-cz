---
title: Komentáře k úkolu
description: Přidání komentáře k úkolu do kódu
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 562DCB46-D8FA-4DC4-AAEA-F274448C4CD2
ms.openlocfilehash: 44d82becfbf3a16ccd2158ac05e171e8530cd721
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2018
ms.locfileid: "42624150"
---
# <a name="task-comments"></a>Komentáře k úkolu

Při psaní kódu, se standardním postupem chcete explicitně přidat komentář nedokončené nebo problematického kódu a rychlé řešení s upozorněními. Tokeny signál výchozí poskytovaný sadou Visual Studio for Mac jsou TODO, HACK, FIXME a VRÁCENO. Individuální tokeny lze definovat v rámci **sady Visual Studio > Předvolby... > prostředí > úlohy**, jak je znázorněno na následujícím obrázku:

 ![Předvolby seznamu úkolů](media/source-editor-image10.png)

Chcete-li přidat nový komentář k úkolu, přidejte komentář, který obsahuje klíčové slovo úloh. Příklad:

```csharp
//TODO: Finish this for all properties.
```

Visual Studio pro Mac zdůrazňující tyto značky zvýrazněním v oblasti úloh, které je možné zobrazit tak, že přejdete do **zobrazení > panely > úkol**:

![Panel seznamu úloh](media/source-editor-image11.png)