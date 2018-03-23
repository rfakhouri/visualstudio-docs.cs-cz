---
title: Vytvoření prostředí pro vývoj Node.js s kontejnery pomocí Kubernetes v cloudu – krok 6 – Další informace o vývoj v týmu | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: ghogen
ms.openlocfilehash: 4db1d71c96da29a06884e562a277a7ca427910d4
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>Začínáme v připojeném prostředí s Node.js

Předchozí krok: [volání služby spuštěné v samostatných kontejneru](get-started-nodejs-05.md)

[!INCLUDE[](includes/team-development-1.md)]

Pojďme pozorování v akci:
1. Přejděte do okna VS Code pro `mywebapi` a ujistěte se, kód upravit výchozí GET `/` obslužnou rutinu, např.:

```javascript
app.get('/', function (req, res) {
    res.send('mywebapi now says something new');
});
```

[!INCLUDE[](includes/team-development-2.md)]

> [!div class="nextstepaction"]
> [Next](get-started-nodejs-07.md)

