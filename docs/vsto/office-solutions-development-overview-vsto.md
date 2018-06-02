---
title: Přehled vývoje řešení pro systém Office (VSTO)
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- primary interop assemblies, Office
- Office development in Visual Studio, about developing solutions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 41fe3ab24b3b70c4cef596caa35c0b4173aaa8fd
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34694027"
---
# <a name="office-solutions-development-overview-vsto"></a>Přehled vývoje řešení pro systém Office (VSTO)
  Pomocí aplikace Microsoft Office jako front-endu řešení můžete využít výhod známé Microsoft Office uživatelská rozhraní a nástroje, jako je funkce zpracování textu v aplikaci Word, funkce analýzy dat aplikace Excel a funkcím pro správu e-mailu aplikace Outlook . Můžete vyvinout řešení v sadě Visual Studio k přizpůsobení aplikace Office a přidání specifické funkce, které jsou potřeba pro své obchodní procesy. Například můžete zapnout Word do generátor kontrakt, který sestaví kontrakty se existující částí, které lze upravovat nebo ne upravovat. V aplikaci Excel můžete vytvořit listu aplikace automatizované nároky přizpůsobené pro různé projekty. Vaši uživatelé můžete taky využít řešení pro systém office do offline režimu, které umožňuje komplexní řešení praktičtější, než by se použily, pokud používáte architekturu založenou na web.  
  
 Toto téma obsahuje přehled typů řešení pro systém Office, které můžete vytvořit pomocí sady Visual Studio Tools pro sadu Office (VSTO) šablony dostupné v Office developer tools v sadě Visual Studio. Obecné informace o tom, jak vyvíjet s Office, najdete v článku [Office developer center](https://dev.office.com/).  
  
## <a name="choose-an-office-project-type"></a>Zvolte typ projektu Office  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] poskytuje následující typy šablon projektu pro vývoj pro Office na základě VSTO:  
  
-   **Úpravy na úrovni dokumentů** konkrétní dokumentu nejsou přidruženy.  
  
-   **Doplňků VSTO** jsou spojeny s vlastní aplikace.  
  
 Rozhodnout, které z těchto typů projektu je nejvhodnější pro vaše řešení, přemýšlení o tom, jestli chcete, aby váš kód pro spuštění jenom v případě určitého dokumentu je otevřené, nebo jestli se mají kódu být k dispozici vždy, když aplikace běží. Další informace o šablonách projektů najdete v tématu [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md).  
  
 Typy projekty, které vytvoříte, závisí na aplikace Office, které jste nainstalovali na vývojovém počítači. Další informace najdete v tématu [dostupné funkce podle aplikace a projekt typu Office](../vsto/features-available-by-office-application-and-project-type.md).  
  
### <a name="document-level-customizations"></a>Přizpůsobení na úrovni dokumentu  
 Úpravy na úrovni dokumentů obsahovat sestavení, které souvisí s jedním dokumentem, sešitu nebo šablony v aplikaci Microsoft Office Word nebo Microsoft Office Excel. Sestavení je načten při přidružené dokumentu. Funkce úpravy, které vytvoříte jsou k dispozici pouze při otevřené přidružené dokumentu. Přizpůsobení nelze provádět změny celou aplikaci, například zobrazení novou kartu položku nebo pásu karet nabídky v otevřeném dokumentu.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] obsahuje nástroje, které vám pomůžou vytvořit úpravy na úrovni dokumentů. Dokument, který upravíte je umístěn jako návrhové ploše v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], což umožňuje návrh dokumentu pomocí přetahování a vkládání ovládacích prvků na něj. Mnoho dalších [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] funkce jsou dostupné v projektech na úrovni dokumentu, jako jsou ovládací prvky Windows Forms, přetažení myší datové vazby a integrované ladicí program.  
  
 Další informace o přizpůsobení najdete v následujících tématech:  
  
-   [Začínáme s programováním přizpůsobení na úrovni dokumentu pro Excel](../vsto/getting-started-programming-document-level-customizations-for-excel.md)  
  
-   [Začínáme s programováním přizpůsobení na úrovni dokumentu pro Word](../vsto/getting-started-programming-document-level-customizations-for-word.md)  
  
-   [Architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md)  
  
### <a name="vsto-add-ins"></a>Doplňků VSTO  
 Doplňků VSTO obsahovat sestavení, které je přidružen k aplikaci Microsoft Office. Obvykle doplňku VSTO spustí při spuštění v přidružené aplikaci, i když uživatelé můžete také načíst doplňků VSTO po aplikace je již spuštěna. Funkce doplňků VSTO vytvořených jsou k dispozici pro aplikaci samostatně, bez ohledu na to, které jsou otevřené dokumenty.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] obsahuje nástroje, které vám pomůžou vytvořit doplňků VSTO. Doplněk projekty patří automaticky generované třídy, která představuje doplňku VSTO. Tato třída poskytuje vlastnosti a události, které můžete použít pro přístup k modelu objektu hostitelské aplikace a spuštění kódu při doplňku VSTO načíst a vypnout. Mnoho dalších [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] funkce jsou dostupné v doplňku VSTO projektech, jako jsou Windows Forms a integrované ladicí program.  
  
 Další informace o doplňků VSTO najdete v následujících tématech:  
  
-   [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)  
  
-   [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)  
  
## <a name="automate-office-applications-by-using-primary-interop-assemblies"></a>Automatizace aplikací Office za použití primární spolupráce – sestavení  
 Můžete-li funkce aplikace Office začlenit do řešení prostřednictvím kódu programu, psaní kódu, který má přístup k modelu objektu aplikace. Objektové modely jsou uspořádání třídy, které zveřejňují funkce prostřednictvím různé vlastnosti a metody. Objektový model pro každou aplikaci Office se liší.  
  
 Chcete-li použít objektový model aplikace systému Office z řešení vytvořené pomocí nástrojů pro vývoj pro Office v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], je nutné použít primární spolupracující sestavení (PIA) pro aplikaci. PRIMÁRNÍ povoluje spravovaného kódu v řešení pro interakci s modelem COM na objekt z aplikace Office.  
  
 Musíte mít PIA Office nainstalovaných a zaregistrovaných v globální mezipaměti sestavení ve svém vývojovém počítači k provádění většiny úloh vývoj. Další informace najdete v tématu [konfigurace počítače pro vývoj řešení pro systém Office](../vsto/configuring-a-computer-to-develop-office-solutions.md). PIA Office nejsou na počítačích koncových uživatelů se vyžaduje spuštění řešení pro systém Office VSTO. Další informace najdete v tématu [návrhu a vytvářet řešení systému Office](../vsto/designing-and-creating-office-solutions.md).  
  
 Další informace o používání v řešeních pro systém Office VSTO PIA najdete v následujících tématech:  
  
-   [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)  
  
-   [Primární spolupracující sestavení sady Office](../vsto/office-primary-interop-assemblies.md)  
  
## <a name="run-microsoft-vsto-office-solutions-on-end-user-computers"></a>Spuštění aplikace Microsoft Office VSTO řešení na počítačích koncových uživatelů  
 Když vytvoříte řešení VSTO Office, zvažte, jak požadavcích nasazení může ovlivnit vaše možnosti vývoje.  
  
### <a name="deployment-options"></a>Možnosti nasazení  
 Použití ClickOnce nebo instalační služba systému Windows k nasazení řešení, které vytvoříte pomocí nástrojů pro vývoj pro Office v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. ClickOnce – nasazení umožňuje vytvářet řešení automatických aktualizací, které můžete nainstalovat a spustit s minimálním uživatelským interakci. Instalační služba systému Windows (*.msi*) soubory mohou být snadno distribuován do počítače koncového uživatele, nebo distribuována pomocí Systems Management Server (SMS). Další informace o nasazení řešení VSTO Office najdete v tématu [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
### <a name="install-prerequisites"></a>Instalace požadovaných součástí  
 Před spuštěním řešení koncoví uživatelé vytvoříte pomocí nástrojů pro vývoj pro Office v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], jejich počítače musí mít nainstalovány některé požadované součásti. Pokud nasadíte řešení pomocí ClickOnce nebo vytváření souboru Instalační služby systému Windows, lze tyto součásti nainstalovat s vaším řešením. Další informace najdete v tématu [požadavky řešení Office na nasazení](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e) a [postupy: instalace požadovaných součástí na koncové uživatele počítačů ke spouštění řešení pro systém Office](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98).  
  
### <a name="security"></a>Zabezpečení  
 Zabezpečení pro řešení pro systém Office VSTO je vynucené řadu kontroluje, zda [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] vytvoří při instalaci a načte řešení. Tyto kontroly zahrnují ověření, zda umístění manifestu nasazení je důvěryhodný, nebo zda je důvěryhodný certifikát použitý k podepsání manifestu nasazení. Další informace najdete v tématu [řešení zabezpečení Office](../vsto/securing-office-solutions.md).  
  
## <a name="see-also"></a>Viz také:  
 [Začínáme &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Začínáme s programováním přizpůsobení na úrovni dokumentu pro Excel](../vsto/getting-started-programming-document-level-customizations-for-excel.md)   
 [Začínáme s programováním přizpůsobení na úrovni dokumentu pro Word](../vsto/getting-started-programming-document-level-customizations-for-word.md)   
 [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)  
  
  