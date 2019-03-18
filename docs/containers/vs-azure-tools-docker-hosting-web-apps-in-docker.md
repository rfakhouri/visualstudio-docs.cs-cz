---
title: Nasazení kontejneru Dockeru ASP.NET do Azure Container Registry (ACR) | Dokumentace Microsoftu
description: Zjistěte, jak nasadit webovou aplikaci ASP.NET Core do registru kontejnerů pomocí Visual Studio Tools for Docker
ms.prod: ''
services: azure-container-service
author: ghogen
manager: jillfra
ms.assetid: e5e81c5e-dd18-4d5a-a24d-a932036e78b9
ms.devlang: dotnet
ms.topic: article
ms.technology: vs-azure
ms.date: 03/14/2019
ms.author: ghogen
ms.openlocfilehash: 346c26a4abe9fd3a28f7d9f711971386fbf1d815
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58149254"
---
# <a name="deploy-an-aspnet-container-to-a-container-registry-using-visual-studio"></a>Nasazení kontejneru ASP.NET do registru kontejneru pomocí sady Visual Studio

## <a name="overview"></a>Přehled

Docker je modul jednoduchý kontejner, podobně jako v některých ohledech k virtuálnímu počítači, který můžete použít k hostování aplikací a služeb.
Tento kurz vás provede kontejnerizované aplikace můžete publikovat pomocí sady Visual Studio [Azure Container Registry](https://azure.microsoft.com/services/container-registry).

Pokud ještě nemáte předplatné Azure, vytvořte si [bezplatný účet](https://azure.microsoft.com/free/dotnet/?utm_source=acr-publish-doc&utm_medium=docs&utm_campaign=docs) před tím, než začnete.

## <a name="prerequisites"></a>Požadavky

K provedení kroků v tomto kurzu je potřeba:

::: moniker range="vs-2017"
* Nainstalujte nejnovější verzi [Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)s úlohou "vývoj aplikací ASP.NET a web"
::: moniker-end
::: moniker range=">=vs-2019"
* Nainstalujte nejnovější verzi [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+rc) s úlohou "vývoj aplikací ASP.NET a web"
::: moniker-end
* Nainstalujte [Docker pro Windows](https://docs.docker.com/docker-for-windows/install/)

## <a name="create-an-aspnet-core-web-app"></a>Vytvoření webové aplikace ASP.NET Core
Následující kroky vás provedou vytvořením základní aplikaci ASP.NET Core, který se použije v tomto kurzu.

::: moniker range="vs-2017"
[!INCLUDE [create-aspnet5-app](../azure/includes/create-aspnet5-app.md)]
::: moniker-end
::: moniker range=">=vs-2019"
[!INCLUDE [create-aspnet5-app](../azure/includes/vs-2019/create-aspnet5-app-2019.md)]
::: moniker-end

## <a name="publish-your-container-to-azure-container-registry"></a>Publikování vašeho kontejneru do služby Azure Container Registry
1. Klikněte pravým tlačítkem na projekt v **Průzkumníka řešení** a zvolte **publikovat**.
2. V dialogovém okně Publikovat cíl, vyberte **Container Registry** kartu.
3. Zvolte **nový registr kontejneru Azure** a klikněte na tlačítko **publikovat**.
4. Vyplňte požadované hodnoty v **vytvořit nový registr kontejneru Azure**.

    | Nastavení      | Navrhovaná hodnota  | Popis                                |
    | ------------ |  ------- | -------------------------------------------------- |
    | **DNS Prefix** | Globálně jedinečný název | Název, který jednoznačně identifikuje vašeho registru kontejneru. |
    | **Předplatné** | Vaše předplatné | Předplatné Azure používat. |
    | **[Skupina prostředků](/azure/azure-resource-manager/resource-group-overview)** | myResourceGroup |  Název skupiny prostředků, ve kterém chcete vytvořit registr kontejnerů. Zvolte **nový** vytvořit novou skupinu prostředků.|
    | **[SKLADOVÁ POLOŽKA](https://docs.microsoft.com/azure/container-registry/container-registry-skus)** | Standard | Úrovně služby do registru kontejneru  |
    | **Umístění registru** | Vám nejbližším místě | Zvolte umístění, do [oblasti](https://azure.microsoft.com/regions/) vaší blízkosti nebo v blízkosti jiných služeb, které budou používat službu container registry. |

    ![Visual Studio vytvořit dialogové okno Azure Container Registry](media/vs-azure-tools-docker-hosting-web-apps-in-docker/vs-acr-provisioning-dialog.png)

5. Klikněte na **Vytvořit**.

Můžete nyní využít kontejneru z registru na každém hostiteli podporuje spuštění imagí Dockeru, například [Azure Container Instances](/azure/container-instances/container-instances-tutorial-deploy-app).