---
title: 'Krok 5: Nasazení aplikace ASP.NET Core do Azure'
description: Nasazení webové aplikace ASP.NET Core do Azure s touto Výukové video a podrobné pokyny.
ms.custom: get-started
ms.date: 03/31/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
monikerRange: vs-2019
ms.topic: tutorial
ms.devlang: CSharp
author: ardalis
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 2d995818ec5b8ac01c9776bbf2290da39d2cc40b
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2019
ms.locfileid: "59018100"
---
# <a name="step-5-deploy-your-aspnet-core-app-to-azure"></a>Krok 5: Nasazení aplikace ASP.NET Core do Azure

Postupujte podle těchto kroků nasadíte aplikaci ASP.NET Core a její databáze do Azure.

_Podívejte se na video a můžete pokračovat k nasazení vaší první aplikace ASP.NET Core do Azure._

> [!VIDEO https://www.youtube.com/embed/n8wz_f5_4wI]

## <a name="open-your-project"></a>Otevřete svůj projekt

Otevřete aplikaci ASP.NET Core v aplikaci Visual Studio 2019. Aplikace musí již být pomocí sady s EF Core a pracovní webové rozhraní API, podle konfigurace v [kroku 4 v této sérii kurzů](tutorial-aspnet-core-ef-step-04.md).

## <a name="publish-to-azure-app-service"></a>Publikování do Azure App Service

Klikněte pravým tlačítkem na projekt v Průzkumníku řešení a zvolte **publikovat**. Ponechejte výchozí nastavení pro položky **služby App Service** a **vytvořit nový** a klikněte na tlačítko **publikovat** tlačítko. Pokud ještě nemáte účet Azure, klikněte na tlačítko **vytvořte si bezplatný účet Azure** a dokončit proces registrace (BRIEF).

Přidáte SQL Server. Zadejte uživatelské jméno správce a heslo.

![Visual Studio 2019 Create Azure SQL Server](media/vs-2019/vs2019-azure-sql-server.png)

Přidejte Application Insights.

Klikněte na tlačítko **vytvořit** tlačítko Pokračovat.

![Visual Studio 2019 vytvořit novou službu Azure App Service](media/vs-2019/vs2019-azure-create-new-app-service.png)

## <a name="exploring-the-azure-portal-and-your-hosted-app"></a>Zkoumání na webu Azure portal a hostované aplikace

Po vytvoření služby app service, spustí se váš web v prohlížeči. Zatímco je načítán můžete také najít služby App Service na webu Azure Portal. Zkoumání dostupné možnosti pro službu app service, zjistíte, **přehled** části, kde lze spustit a zastavit aplikaci.

![Možnosti služby Azure App Service](media/vs-2019/vs2019-azure-app-service-menu-options.png)

### <a name="scalability"></a>Škálovatelnost

Můžete prozkoumat možnosti stejně jako na škálování aplikace. Vertikální navýšení kapacity odkazuje na zvýšit množství prostředků uvedené jednotlivým instancím, které hostují vaši aplikaci. Horizontální navýšení kapacity odkazuje na zvýšení počtu instancí, které hostují vaši aplikaci. Konfigurace automatického škálování pro vaši aplikaci, která bude automaticky zvýšit počet instancí, které používají k hostování vaší aplikace v reakci na zatížení a jakmile se snížila zátěž jejich omezení.

### <a name="security-and-compliance"></a>Zabezpečení a dodržování předpisů

Další výhodou hostování vaší aplikace pomocí Azure je zabezpečení a dodržování předpisů. Azure App Service poskytuje ISO, SOC a PCI dodržování předpisů. Abychom si mohli vybrat pro ověřování uživatelů pomocí Azure Active Directory nebo přihlašování přes sociální sítě jako je Twitter, Facebook, Google nebo Microsoft. Jsme můžete vytvořit omezení IP adres, spravovat identity služby, přidávat vlastní domény a podporují SSL pro aplikaci, jakož i Konfigurace zálohování s obnovitelné kopie archivu obsahu, konfigurace a databáze aplikace. Tyto funkce jsou přístupné z ověřování / autorizace, Identity, zálohování, nastavení SSL a možnosti nabídky.

### <a name="deployment-slots"></a>Nasazovací sloty

Často při nasazení aplikace je malé dobu výpadku během restartování aplikace. Sloty nasazení se tomuto problému vyhnout, neboť umožňuje nasadit samostatnou instanci pracovní nebo sadu instancí a tyto zahřívání před přechodem do produkčního prostředí. Prohození je jenom rychlé a bezproblémové provozu přesměrování. Pokud existují nějaké problémy v produkčním prostředí po prohození, můžete vždy zaměnit zpět do vaší poslední známé dobré provozního stavu.

## <a name="update-connection-string"></a>Aktualizace připojovacího řetězce

Ve výchozím nastavení Azure očekává, že novou aplikaci připojení ke své nové databáze SQL serveru použít připojovací řetězec s názvem `DefaultConnection`. Aktuálně aplikace jsme vytvořili dříve v této sérii kurzů používá připojovací řetězec s názvem `AppDbContext`. Chcete změnit to *appsettings.json* a *Startup.cs* a potom aplikaci znovu nasaďte.

## <a name="test-the-app-running-in-azure"></a>Otestujte aplikaci spuštěnou v Azure

Přejděte */hry* cestě a měl přidat novou hru a nezobrazuje. Dále přejděte */swagger* cesta kde měl pomocí koncových bodů webové rozhraní API z něj potvrďte aplikace API také pracuje.

Blahopřejeme! Dokončili jste tuto sérii kurzů videích!

## <a name="next-steps"></a>Další kroky

Další informace o tom, jak navrhovat aplikace ASP.NET Core s tyto bezplatné prostředky.

[Architektura aplikace ASP.NET Core](https://dotnet.microsoft.com/learn/web/aspnet-architecture)

## <a name="see-also"></a>Viz také:

- [Publikování aplikace ASP.NET Core do Azure pomocí sady Visual Studio](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.2)