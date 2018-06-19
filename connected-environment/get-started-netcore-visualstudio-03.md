---
title: Vytvoření prostředí pro vývoj .NET Core s kontejnery pomocí Kubernetes v cloudu pomocí sady Visual Studio – krok 3 – vytvoření prostředí pro vývoj Kubernetes | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: 6226340b1744e95bbb375d47213ae00bb9e76565
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31884382"
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>Začínáme v připojeném prostředí s .NET Core a Visual Studio

Předchozí krok: [vytvořit rozhraní ASP.NET web apps](get-started-netcore-visualstudio-02.md)

## <a name="create-a-dev-environment-in-azure"></a>Vytvořte vývojová prostředí v Azure
S prostředím připojen můžete vytvořit na základě Kubernetes vývojových prostředí, které jsou plně spravované službou Azure a optimalizovaná pro vývoj. S projektem jsme právě vytvořili otevřený, vyberte **připojené prostředí pro AKS** z rozevíracího seznamu k nastavení spustit jak je uvedeno níže.

![](images/LaunchSettings.png)

V dialogovém okně se zobrazí vedle zkontrolujte, zda jste přihlášeni pomocí účtu odpovídající účet a poté buď vyberte existující vývojové prostředí nebo vyberte **< vytvořit nové připojení prostředí pro AKS... >** vytvořit nový.

![](images/ConnectedEnvDialog.png)

Můžete použít výchozí hodnoty zadaný nebo je upravit podle potřeby. Klikněte na tlačítko **OK** při hodnoty jsou nastaveny správně.

![](images/NewEnvDialog.png)

Zpět na do předchozího dialogového okna nechte **místo** rozevíracího seznamu uvedena do výchozího stavu `mainline` prozatím se budeme zabývat tím později podrobněji. Zkontrolujte **veřejně přístupná** zaškrtávací políčko, budou přístupné přes veřejný koncový bod webové aplikace. Tato akce není povinná, ale může být vhodné k předvedení některé pojmy dále v tomto návodu. Ale nemusíte si dělat starosti, v obou případech bude možné k ladění webu pomocí sady Visual Studio.

![](images/ConnectedEnvDialog2.png)

Klikněte na tlačítko **OK** a vyberte nebo vytvořte vývojové prostředí. Spustí se úlohy na pozadí k tomu, bude trvat několik minut. Se zobrazí, pokud ho stále probíhá vytváření ukázáním kurzor **úlohy na pozadí** ikonu v levém dolním rohu stav panelu (viz níže).

![](images/BackgroundTasks.png)

> [!Note]
Dokud se úspěšně vytvořil vývojového prostředí nelze ladění aplikace.

## <a name="look-at-the-files-added-to-project"></a>Podívejte se na soubory přidané do projektu
Když jsme počkejte vývojového prostředí, který se má vytvořit, podíváme se na soubory, které jsou přidané do projektu, když jste se rozhodli použít vývojové prostředí.

Nejprve se zobrazí složka s názvem `charts` byl přidaný a v rámci to [Helm grafu](https://docs.helm.sh) pro vaše aplikace byla vygeneroval. Tyto soubory se používají k nasazení aplikace do vývojového prostředí.

Zobrazí se soubor s názvem `Dockerfile` byla přidána. Tento soubor obsahuje informace potřebné k balíčku aplikace ve standardním formátu Docker. A `HeaderPropagation.cs` také k vytvoření souboru, se budeme zabývat tento soubor později v tomto návodu. 

Nakonec uvidíte soubor s názvem `vsce.yaml` obsahující informace o konfiguraci, která je potřeba vývojového prostředí, například jestli by aplikace měla být přístupné přes veřejný koncový bod.

![](images/ProjectFiles.png)

> [!div class="nextstepaction"]
> [Ladění kontejner v Kubernetes](get-started-netcore-visualstudio-04.md)