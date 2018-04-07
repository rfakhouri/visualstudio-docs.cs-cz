---
title: Vytvoření prostředí pro vývoj .NET Core s kontejnery pomocí Kubernetes v cloudu pomocí nástrojů Visual Studio – krok 1 – instalace | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 04/05/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: ghogen
ms.openlocfilehash: 64aa0b322c777baa78da5bf86cb1220a47128d93
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/06/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>Začínáme v připojeném prostředí s .NET Core a Visual Studio

V tomto průvodci se dozvíte, jak:

1. Vytvořte prostředí na základě Kubernetes v Azure, která je optimalizovaná pro vývoj.
1. Opakované vývoj kódu v kontejnerech pomocí sady Visual Studio.
1. Vývoj nezávisle dvě samostatné služby a použít Kubernetes zjišťování služby DNS k volání na jinou službu.
1. Produktivní vývoj a testování kódu v prostředí team.

[!INCLUDE[](includes/see-troubleshooting.md)]

## <a name="install-the-connected-environment-cli"></a>Nainstalujte připojeném prostředí rozhraní příkazového řádku
Připojeném prostředí vyžaduje nastavení minimální místního počítače. Velká část konfigurace vývojového prostředí získá uložených v cloudu a je ke sdílení s jinými uživateli.

1. Stažení a spuštění [připojené Instalační služby rozhraní příkazového řádku prostředí](https://aka.ms/get-vsce-windows). 

## <a name="get-kubernetes-debugging-tools"></a>Získat Kubernetes nástroje pro ladění
I když můžete pomocí rozhraní příkazového řádku prostředí připojené jako samostatný nástroj, bohaté funkce, jako jsou **Kubernetes ladění** jsou k dispozici pro vývojáře .NET Core pomocí **VS Code** nebo **Visual Studio** .

### <a name="visual-studio-debugging"></a>Ladění Visual Studio 
1. Nainstalujte nejnovější verzi [Visual Studio 2017](https://www.visualstudio.com/vs/)
1. V instalačním programu sady Visual Studio Ujistěte se, že je vybraný následující úlohy:
    * ASP.NET a vývoje
1. Nainstalujte [rozšíření sady Visual Studio pro připojené prostředí](https://aka.ms/get-vsce-visualstudio)

Nyní jsme připraveni k vytvoření webové aplikace ASP.NET pomocí sady Visual Studio.

> [!div class="nextstepaction"]
> [Vytvoření webové aplikace ASP.NET](get-started-netcore-visualstudio-02.md)
