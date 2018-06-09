---
title: Kurz nástroje Kubernetes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2018
ms.technology: vs-ide-deployment
ms.topic: conceptual
author: ghogen
ms.author: ghogen
manager: douge
ms.workload:
- azure
ms.openlocfilehash: a2bdc24a3e1ee30ffa569fa0c9e5b2ab208aa7ef
ms.sourcegitcommit: 886759fb35a88f6ef5452c5b2e33a1f71da4489a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/08/2018
ms.locfileid: "34851891"
---
# <a name="get-started-with-visual-studio-kubernetes-tools"></a>Začínáme s Kubernetes nástroje sady Visual Studio

Visual Studio Kubernetes Tools zjednodušit vývoj cílení na Kubernetes kontejnerizované aplikací. Visual Studio můžete automaticky vytvořit jako kód konfigurace soubory potřebné k podpoře Kubernetes nasazení, například Dockerfiles a Helm grafy. Kromě toho můžete publikovat přímo do clusteru Azure Kubernetes služby (AKS) ze sady Visual Studio.

## <a name="prerequisites"></a>Požadavky

Můžete využít tyto nové funkce, budete potřebovat:

- Nejnovější verzi preview [Visual Studio 2017](https://www.visualstudio.com/vs/preview) se zatížením, vývoj pro Azure.

- [Kubernetes tools pro Visual Studio](https://aka.ms/get-vsk8stools), k dispozici jako samostatný soubor ke stažení.

- [Docker pro systém Windows](https://store.docker.com/editions/community/docker-ce-desktop-windows) nainstalován na stanici vývoje (to znamená, kde spouštíte Visual Studio)

- Pokud chcete publikovat do AKS ze sady Visual Studio:

    1.  [AKS publikování nástroje](https://aka.ms/get-vsk8spublish), k dispozici jako samostatný soubor ke stažení.

    1.  Cluster Azure Kubernetes Service. Další informace najdete v tématu [vytváření clusteru služby AKS](/azure/aks/kubernetes-walkthrough-portal#create-aks-cluster). Nezapomeňte [připojte se ke clusteru](/azure/aks/kubernetes-walkthrough#connect-to-the-cluster) z vaší pracovní stanici.

    1.  Helm CLI nainstalovaná na pracovní stanici. Další informace najdete v části [instalace Helm](https://github.com/kubernetes/helm/blob/master/docs/install.md).

    1.  Helm nakonfigurovaný pro váš cluster AKS. Další informace o tom, jak to udělat najdete v tématu [postup konfigurace Helm](/azure/aks/kubernetes-helm#configure-helm).

## <a name="create-a-new-kubernetes-project"></a>Vytvoření nového projektu Kubernetes

Jakmile máte příslušné nástroje nainstalované, spusťte sadu Visual Studio a vytvořte nový projekt. V části **cloudu**, vyberte **aplikace kontejnerů pro Kubernetes** typ projektu. Vyberte tento typ projektu a zvolte **OK**.

![Snímek obrazovky vytvoření nového projektu aplikace Kubernetes](media/k8s-tools-new-k8s-app.png)

Potom můžete typu ASP.NET Core k vytvoření webové aplikace. Zvolte **webové aplikace** a zvolte **OK**. Obvyklé **povolení podpory Docker** možnost nezobrazí v tomto dialogovém okně.  Podpora docker je povolena ve výchozím nastavení pro aplikace kontejnerů pro Kubernetes.

![Snímek obrazovky výběru webové aplikace](media/k8s-tools-web-app-selection-screen.png)

## <a name="add-kubernetes-support-to-an-existing-project"></a>Přidání podpory Kubernetes do existujícího projektu

Alternativně můžete přidat podporu Kubernetes existující projekt webové aplikace ASP.NET Core. Chcete-li to provést, klikněte pravým tlačítkem na projekt a zvolte **přidat** > **podpora kontejnerů Orchestrator**.

![Snímek obrazovky z přidat kontejner Orchestrator položky nabídky](media/k8s-tools-add-container-orchestrator.png)

V dialogovém okně vyberte "Kubernetes/Helm" a zvolte **OK**.

![Dialogové okno snímek obrazovky z přidat kontejner Orchestrator](media/k8s-tools-add-container-orchestrator-dialog-box.PNG)

## <a name="what-visual-studio-creates-for-you"></a>Visual Studio vytvoří pro vás

Po vytvoření nové **aplikace kontejnerů pro Kubernetes** projektu nebo přidání podpory orchestrator kontejneru Kubernetes do existujícího projektu, se zobrazí některé další soubory, které usnadňují nasazování do Kubernetes ve vašem projektu.

![Snímek obrazovky nástroje Průzkumník řešení po přidání podpory Orchestrator kontejneru](media/k8s-tools-solution-explorer.png)

Přidané soubory jsou:

- soubor Docker, což vám umožní generovat Docker kontejneru image hostování této webové aplikace. Jak zjistíte, nástrojů Visual Studio využívá tento soubor Docker při ladění a nasazení do Kubernetes. Pokud dáváte přednost pracovat přímo s bitovou kopii Docker, můžete kliknout pravým tlačítkem na soubor Docker a zvolte **sestavení Image Docker**.

   ![Snímek obrazovky nástroje sestavení Docker Image možnost](media/k8s-tools-build-docker-image.png)

- Graf Helm a *grafy* složky. Tyto soubory yaml tvoří Helm graf pro aplikaci, které můžete použít k nasazení do Kubernetes. Další informace o Helm najdete v tématu [ https://www.helm.sh ](https://www.helm.sh).

- *azds.yaml*. Tato položka obsahuje nastavení pro prostory Dev Azure, novou službu, která poskytuje rychlé, iterační ladění prostředí ve službě Azure Kubernetes Service. Tento soubor je aktuálně nepoužívané, ale je rezervovaná pro budoucí použití mezerami Dev Azure.

## <a name="publish-to-azure-kubernetes-service-aks"></a>Publikování do služby Azure Kubernetes (AKS)

Všechny tyto soubory na místě můžete pomocí prostředí Visual Studio IDE k zápisu a ladění kódu aplikace, stejně, jako je navíc vždy nutné.

Jakmile máte váš kód spuštěný způsob, jakým chcete, můžete publikovat přímo ze sady Visual Studio k AKS clusteru.

Chcete-li to provést, musíte nejprve nastavit profil publikování, který publikuje kontejneru image do Azure kontejneru registru (ACR). Potom můžete AKS načítat kontejneru image z ACR a nasadit do clusteru.

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na vaše *projektu* a zvolte **publikovat**.

   ![Snímek obrazovky publikování položky nabídky](media/k8s-tools-publish-project.png)

1. V **publikovat** obrazovky, zvolte **kontejneru registru** jako publikování cíle a podle pokynů vyberte kontejner registr. Pokud ještě nemáte kontejner registru, zvolte **vytvořit nové registru kontejner Azure** Chcete-li vytvořit ze sady Visual Studio. Další informace najdete v tématu [publikování vašeho kontejneru do registru kontejner Azure](#publish-your-container-to-azure-container-registry).

   ![Snímek obrazovky vyberte cílovou obrazovku publikování](media/k8s-tools-publish-to-acr.png)

1. Zpět v Průzkumníku řešení klikněte pravým tlačítkem na vaše *řešení* a klikněte na tlačítko **publikovat na Azure AKS**.

   ![Snímek obrazovky publikovat do Azure AKS položky nabídky](media/k8s-tools-publish-solution.png)

1. Zvolte předplatné a AKS cluster, společně s ACR Publikovat profil, který jste právě vytvořili. Pak klikněte na tlačítko **OK**.

   ![Snímek obrazovky publikovat na obrazovku AKS](media/k8s-tools-publish-to-aks.png)

   Tím přejdete **publikovat na Azure AKS** obrazovky.

1.  Vyberte **konfigurace Helm** odkaz Aktualizovat příkazovým řádkem použitým k instalaci Helm grafy na serveru.

   ![Snímek obrazovky konfigurace Helm odkaz](media/k8s-tools-configure-helm.png)

   Aktualizace příkazového řádku je užitečné, pokud existují argumenty vlastní příkazového řádku, které chcete určit, jako je například jiný Kubernetes kontext nebo grafu název.

   ![Screenshoot Helm Konfigurace obrazovky](media/k8s-tools-helm-configure-screen.png)

1. Jakmile budete připraveni k nasazení, klikněte **publikovat** tlačítko pro publikování aplikace do AKS.

   ![Snímek obrazovky publikovat na obrazovku Azure AKS](media/k8s-tools-publish-screen.png)

Blahopřejeme! Nyní můžete potenciál Visual Studio pro všechny vývoj Kubernetes aplikací.

## <a name="next-steps"></a>Další kroky

Další informace o Kubernetes vývoj na platformě Azure načtením [AKS dokumentaci](/azure/aks).