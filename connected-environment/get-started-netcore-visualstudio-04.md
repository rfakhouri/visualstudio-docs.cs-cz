---
title: Vytvoření vývojového prostředí .NET Core s kontejnery pomocí Kubernetes v cloudu pomocí sady Visual Studio – krok 4 – ladění kontejneru v Kubernetes | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: 75588fcabbba739c4670da42e24665428ff89130
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>Začínáme v připojeném prostředí s .NET Core a Visual Studio

Předchozí krok: [vytvořte vývojová prostředí v Azure](get-started-netcore-visualstudio-03.md)

## <a name="debug-a-container-in-kubernetes"></a>Ladění kontejner v Kubernetes
Po úspěšném vytvoření vývojového prostředí můžete ladit aplikace. Nastavte zarážky v kódu, například na řádku 20 v souboru `HomeController.cs` kde `Message` proměnná je nastavená. Klikněte na tlačítko **F5** spustit ladění. 

Visual Studio bude komunikovat se vývojové prostředí pro sestavení a nasazení aplikace a pak otevřete v prohlížeči se webová aplikace spuštěná. To nemusí připadat jako kontejner běží místně, ale ve skutečnosti je spuštěna v našem vývojového prostředí v Azure. Z důvodu pro adresu místního hostitele totiž připojené prostředí vytvoří dočasný tunelového propojení SSH ke kontejneru, který běží v Azure.

Klikněte na "**o**" odkaz v horní části stránky pro aktivaci zarážku. Máte plný přístup k ladění informace stejně, jako kdybyste kód se provádí místně, jako je například zásobníku volání, místní proměnné, informace o výjimce, atd.

> [!div class="nextstepaction"]
> [Volání jiného kontejneru](get-started-netcore-visualstudio-05.md)