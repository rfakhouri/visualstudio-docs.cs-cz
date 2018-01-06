---
title: "Návrh a vytváření řešení pro systém Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office solutions [Office development in Visual Studio], creating
- Office development in Visual Studio, creating solutions
- solutions [Office development in Visual Studio], creating
- Office project types in Visual Studio
ms.assetid: 53c32c61-3d3a-4427-a5a7-f9c2c8f1de02
caps.latest.revision: "103"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8b7322faa797ea9ce51af0cd716ffb6536f062ef
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="designing-and-creating-office-solutions"></a>Navrhování a tvorba řešení pro systém Office
  Visual Studio poskytuje šablony projektů, které můžete použít k vytvoření několika různých typů řešení pro systém Office. Tato část dokumentace popisuje šablony projektů a poskytuje pokyny k vytváření projektů Office. Informace o tom, jak implementovat kódu a uživatelské rozhraní přizpůsobení po vytvoření projektu najdete v tématu [vývoj řešení pro systém Office](../vsto/developing-office-solutions.md).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
## <a name="creating-office-projects"></a>Vytváření projektů Office  
 Než začnete, měli byste stanovit požadavky na a zjistit typ řešení, které nabízí nejlepší. Například pokud vaše řešení Office, musíte spustit pokaždé, když aplikace se používá, doplňku VSTO nejlepší pro rozlišení vašim požadavkům. Pokud kód je úzce integrovaná s jedním dokumentem, vytvořte přizpůsobení na úrovni dokumentu. Tyto typy projektů jsou k dispozici jako šablony projektů Visual Studio. Další informace o šablonách projektů Office, které jsou součástí sady Visual Studio najdete v tématu [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md). Další informace o tom, jak vytváření projektů Office najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Projekty Office mají funkcí a položek projektů, které se liší od ostatních typů projektů v sadě Visual Studio. Například při vytváření projektu úrovni dokumentu, dokumentu nebo sešitu v projektu může být otevřít a upravit v sadě Visual Studio. Další informace najdete v tématu [projektech pro systém Office v prostředí sady Visual Studio](../vsto/office-projects-in-the-visual-studio-environment.md).  
  
## <a name="choosing-a-net-framework-version"></a>Výběr verze rozhraní .NET Framework  
 Po výběru typu projektu, které bude nejlépe vyhovovat vašim požadavkům, můžete zvolit, která verze rozhraní .NET Framework pro použití v vývojových procesech. Můžete vybrat následující verze rozhraní .NET Framework v projektech Office:  
  
-   [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]  
  
-   [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)]  
  
-   [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]  
  
 Na počítačích koncových uživatelů pro vaše řešení ke spuštění se vyžaduje verzi rozhraní .NET Framework, který jste vybrali pro váš projekt. Například pokud vaše cíle projektu [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] je potřeba na počítačích koncových uživatelů. V tomto příkladu řešení se nespustí, pokud pouze na počítačích koncového uživatele je nainstalované rozhraní .NET Framework 3.5.  
  
 Pokud provádíte migraci projektu doplňku VSTO, která je cílena na rozhraní .NET Framework 3.5, Visual Studio změní cílový framework projektu na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, v závislosti na verzi systému Office, který jste nainstalovali.  
  
 Po Visual Studio změn cílové rozhraní, může ale muset upravit některé kódu v projektu, pokud používá určité funkce. Další informace o tom, jak změnit cílový framework najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md). Další informace o změnách budete možná muset udělat ve vašem projektu najdete v tématu [migrace řešení pro systém Office na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md).  
  
 Pokud Visual Studio změny cílového rozhraní .NET Framework pro váš projekt a používáte ClickOnce k nasazení řešení, ujistěte se také vyberte odpovídající verzi rozhraní .NET Framework v **požadavky** dialogové okno. Tento výběr nezmění automaticky, když změnit cílový framework projektu. Další informace najdete v tématu [postupy: instalace požadavky v počítačích koncových uživatelů pro spuštění řešení pro systém Office](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98).  
  
> [!NOTE]  
>  Možné vybrat jako cíl rozhraní .NET Framework 3.5 nebo starší v projektech Office, které vytvoříte pomocí [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]. Projekty Office, které vytvoříte pomocí [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] vyžadují funkce, která byla poprvé představena v[!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)]  
  
### <a name="understanding-when-the-office-pias-are-required-on-end-user-computers"></a>Principy při PIA Office, je nutné počítače koncového uživatele  
 Ve výchozím nastavení, primární spolupracující sestavení sady Office (PIA) není potřeba nainstalovat na počítače koncového uživatele, pokud **vložit zprostředkovatel komunikace s objekty typy** každý Office PIA odkazu v projektu je nastavena na **True**, které je to výchozí hodnota. V tomto scénáři informací o typu pro PIA – typy, které se používají ve vašem řešení vložené do sestavení řešení při sestavování projektu. V době běhu informace o vložených typu použít místo PIA pro volání do modelu COM na objekt z aplikace Office. Další informace o tom, jak jsou typy z PIA vkládat do řešení najdete v tématu [ekvivalence typů a vložené typy zprostředkovatel komunikace s objekty](/dotnet/framework/interop/type-equivalence-and-embedded-interop-types).  
  
 Pokud **vložit zprostředkovatel komunikace s objekty typy** každý Office PIA odkazu v projektu je nastavena na **False**, Office PIA musí být nainstalovaný a zaregistrovaný v globální mezipaměti sestavení na každém počítači koncového uživatele, Spustí řešení. Ve většině případů PIA jsou nainstalované ve výchozím nastavení v sadě Office, ale můžete použít také PIA redistributable předpokladem pro vaše řešení. Další informace najdete v tématu [požadavky řešení Office na nasazení](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e).  
  
### <a name="understanding-the-client-profile"></a>Principy profil klienta  
 Profil klienta rozhraní .NET Framework je podmnožinou úplné rozhraní .NET Framework. Pokud budete muset použít pouze klientské funkce v rozhraní .NET Framework a chcete zajistit nejrychlejší možné nasazení prostředí pro řešení Office, můžete vybrat profil klienta rozhraní .NET Framework. Další informace najdete v tématu [profil klienta rozhraní .NET Framework](/dotnet/framework/deployment/client-profile).  
  
 Když vytvoříte projekt Office, s cílem [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)] výchozí cílový. Pokud chcete k vývoji pro celý [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], tato možnost je nutné nastavit po vytvoření projektu. Další informace najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
## <a name="creating-solutions-for-the-64-bit-edition-of-microsoft-office"></a>Vytváření řešení pro 64bitová edice systému Microsoft Office  
 Aplikace Microsoft Office je k dispozici v edicích 64bitové a 32bitové verze. Pokud chcete řešení pro systém Office, které můžou běžet v kteroukoli edici, musí být nastavení cílové platformy pro svůj projekt nastavte na **libovolný procesor**. Toto je výchozí hodnota pro projekty Office. Další informace najdete v tématu [vytváření řešení pro systém Office](../vsto/building-office-solutions.md).  
  
 Existují samostatné 64bitové a 32bitové verze [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] jsou používány v edicích 64bitové a 32bitové verze systému Microsoft Office. Další informace najdete v tématu [Visual Studio Tools for Office Runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
## <a name="assemblies-in-office-solutions"></a>Sestavení v řešeních pro systém Office  
 Když vytvoříte projekt Office pomocí nástrojů pro vývoj pro Office v sadě Visual Studio, kód, který můžete psát nakonec zkompilován sestavení. Sestavení je obvykle nasadit na sdílený server nebo do adresáře na klientském počítači.  
  
 Sestavení v řešeních pro systém Office se načítají aplikací systému Office. Po načíst sestavení kódu v sestavení můžete reakce na události, které jsou vyvolány v aplikaci, například když uživatel klikne položku nabídky. Kód v sestavení může také volání do modelu objektu automatizovat a rozšířit aplikace a může použít jakékoli třídy v [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)]. Další informace najdete v tématu [architektura z úpravy na úrovni dokumentů](../vsto/architecture-of-document-level-customizations.md) a [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md).  
  
 Řešení Office slouží k identifikaci sestavení manifestů aplikace a manifesty nasazení. Manifesty obsahují informace o název, verzi a umístění, je sestavení, které aplikace můžete najít, propojit a spustit správná sestavení. Další informace najdete v tématu [aplikace a manifesty nasazení v řešeních pro systém Office](../vsto/application-and-deployment-manifests-in-office-solutions.md).  
  
 Projekty na úrovni dokumentu zahrnují dokumentu kromě sestavení. Dokument funguje jako front-endu aplikace a je, kde probíhá veškerou interakci uživatele. Každý dokument může mít pouze jeden hlavní projekt sestavení přidruženo; více dokumentů však může ukazovat na stejném sestavení.  
  
 Sestavení v projektech na úrovni dokumentu nejsou vložená v dokumentu. Místo toho jsou uložená na jiném místě a jsou určeny dokumentu manifest aplikace.  
  
## <a name="security-considerations-for-assemblies"></a>Důležité informace o zabezpečení pro sestavení  
 Pro řešení Office na spuštění v počítači musí být důvěryhodný pro spuštění sestavení používá řešení. Další informace o zabezpečení najdete v tématu [zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md).  
  
 Ve výchozím nastavení jsou důvěryhodné pro spuštění na vývojovém počítači při sestavování projektu sestavení řešení a všechny odkazované sestavení, které jsou v projektu na výstupní složce. Další informace najdete v tématu [vytváření řešení pro systém Office](../vsto/building-office-solutions.md).  
  
 Z bezpečnostních důvodů je nejvhodnější vytvořit projekty do místního počítače, nikoli vývoj na sdílené umístění. Další informace najdete v tématu [spolupráce vývoj řešení Office](../vsto/collaborative-development-of-office-solutions.md).  
  
## <a name="referenced-assemblies"></a>Odkazovaná sestavení  
 Sestavení může odkazovat na jiné sestavení, které jsou uvedeny v odkazech na projektu. Jeden sestavení v projektech na úrovni dokumentu však nemůže odkazovat na jiné sestavení v projektech na úrovni dokumentu.  
  
## <a name="see-also"></a>Viz také  
 [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Projekty Office v prostředí Visual Studio](../vsto/office-projects-in-the-visual-studio-environment.md)   
 [Vlastnosti v projektech pro systém Office](../vsto/properties-in-office-projects.md)   
 [Spouštění řešení v různých verzích systému Microsoft Office](../vsto/running-solutions-in-different-versions-of-microsoft-office.md)   
 [Postupy: cílení na aplikace Office prostřednictvím primární spolupráce – sestavení](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Manifestů aplikace a nasazení v řešeních pro systém Office](../vsto/application-and-deployment-manifests-in-office-solutions.md)   
 [Postupy: nastavení informací o konfiguraci pro řešení Office](../vsto/how-to-set-up-configuration-information-for-an-office-solution.md)   
 [Použití funkcí systému Office v sadě Visual Studio](../vsto/using-office-functionality-inside-of-visual-studio.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Běžné úlohy při programování pro Office](../vsto/common-tasks-in-office-programming.md)   
 [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)   
 [Architektura řešení pro systém Office v sadě Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md)  
  
  