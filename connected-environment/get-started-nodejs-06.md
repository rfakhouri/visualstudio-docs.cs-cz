---
title: Vytvoření prostředí pro vývoj Node.js s kontejnery pomocí Kubernetes v cloudu – krok 6 – Další informace o vývoj v týmu | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: 6a17dfc3eeebccf1508ea3f69aecb53d067de7af
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
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

