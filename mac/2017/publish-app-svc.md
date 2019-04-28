---
title: Publikování do Azure App Service
ms.date: 01/17/2019
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: 8524a4c5-97a9-41ac-a2a0-034efb9bfc57
author: sayedihashimi
ms.author: sayedha
manager: unniravindranathan
ms.prod: visual-studio-mac
ms.custom: video
ms.workload:
- azure
ms.openlocfilehash: 48cf25a7164fabc96924897c0a4a28bbbe4bea74
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62988596"
---
# <a name="publish-a-web-app-to-azure-app-service-using-visual-studio-for-mac"></a>Publikování webové aplikace do služby Azure App Service pomocí sady Visual Studio pro Mac

Nástroj publikování můžete použít k publikování aplikace ASP.NET Core do služby Azure App Service.

## <a name="prerequisites"></a>Požadavky

- [Visual Studio 2017 for Mac](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs4mac2017) nainstalované s ASP.NET Core povolena.
- Předplatné Azure. Pokud ještě nemáte předplatné, [ZDARMA zaregistrovat](https://azure.microsoft.com/free/dotnet/), což zahrnuje 200 USD v kreditech na 30 dnů a 12 měsíců oblíbených služeb zdarma.
- Projekt ASP.NET Core. Pokud projekt ještě nemáte, můžete si [vytvořte novou](https://docs.microsoft.com/visualstudio/mac/create-new-projects?view=vsmac-2017).

## <a name="publish-to-azure-app-service"></a>Publikování do Azure App Service

 1. V oblasti řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat**.

    ![Místní nabídka publikovat](media/publish-context-menu.png)

 2. Pokud jste dříve publikovali tento projekt do služby Azure App Service, zobrazí se vám v nabídce profilu publikování. Vyberte tento profil publikování, chcete-li zahájit proces publikování.

 3. První přihlášení publikujte tento projekt do služby App Service, vyberte **publikovat do Azure**

    ![Publikování do služby App Service kontextové nabídky](media/publish-to-azure-context-menu.png)

 4. **Publikovat do služby Azure App Service** se zobrazí dialogové okno a jsou uvedeny všechny existující aplikace služby. Publikovat do existující služby App Service, vyberte službu App Service v seznamu a potom klikněte na tlačítko **publikovat**.

    ![Publikování do služby Azure App Service dialogového okna](media/publish-to-app-service-dialog.png)

 5. Chcete-li vytvořit novou službu App Service, klikněte na tlačítko **nový** tlačítko.

    ![Publikování na dialogovém okně App Service](media/publish-to-app-service-dialog-new-selected.png)

 6. **Novou službu App Service** se zobrazí dialogové okno. V tomto dialogovém okně můžete nakonfigurovat nastavení pro novou službu App Service.

    ![Dialogové okno nové služby App Service](media/publish-new-app-service.png)

    Existuje několik možností přizpůsobení tady. Název projektu se výchozí název služby App Service. Pokud název není k dispozici znaménko upozornění se zobrazí na pravé straně vstupní pole. Název služby App Service se použije v adrese URL vašeho webu, takže název musí být platná pro použití v adrese URL.

    Můžete změnit předplatné, že bude spojená s využitím služby App Service **předplatné** rozevíracího seznamu.

    Můžete vybrat existující **skupiny prostředků** pomocí rozevíracího seznamu, nebo můžete vytvořit nový s **+** tlačítko.

    Plán služby App Service, vyberte nějaký existující, nebo vytvořte nové tak, že vyberete **vlastní** přepínač.

    Pokud chcete vytvořit novou službu App Service a publikovat projekt, klikněte na tlačítko **vytvořit**.

    Po kliknutí na tlačítko **vytvořit** **novou službu App Service** dialogové okno se zavře a by se zobrazit následující zpráva označující, zda bylo zahájeno vytváření služby App Service.

      ![Vytvoření služby App Service zprávy](media/publish-create-app-service-message.png)

    Po kliknutí na tlačítko **OK** zpráva se zavře a můžete pokračovat v práci na projektu. Můžete sledovat stav procesu publikování pomocí stavového řádku v horní části rozhraní IDE. Až vaše webová aplikace se úspěšně publikovala, web se otevře s výchozím prohlížeči.

## <a name="related-video"></a>Související videa

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Publish-to-Azure/player]
