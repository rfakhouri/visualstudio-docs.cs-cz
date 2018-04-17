---
title: Projekt podtypů návrhu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project subtypes, design
ms.assetid: 405488bb-1362-40ed-b0f1-04a57fc98c56
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a931d6509b5a8a90f371986f4ddb8955c64387d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="project-subtypes-design"></a>Návrh podtypů projektu
Projekt podtypů umožní VSPackages rozšířit projekty založené na Microsoft Build Engine (MSBuild). Použití agregace, můžete znovu použít hromadné implementované v systému projektu jádro spravované [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ještě stále přizpůsobit chování pro konkrétní scénář.  
  
 V následujících tématech jsou upřesněny základní návrh a implementaci podtypů projektu:  
  
-   Podtyp návrhu projektu.  
  
-   Víceúrovňovou agregace.  
  
-   Podpora rozhraní.  
  
## <a name="project-subtype-design"></a>Podtyp návrhu projektu  
 Inicializace podtypu projektu se dosahuje agregování hlavní <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject> objekty. Tato agregace umožňuje podtypem projektu k přepsání nebo rozšíření většinu funkcí základní projektu. Projekt podtypů získat první příležitosti pro zpracování vlastností pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>, příkazy, pomocí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>a pomocí správy položky projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>. Můžete také rozšířit podtypů projektu:  
  
-   Objekty konfigurace projektu.  
  
-   Konfigurace závislé objekty.  
  
-   Procházet konfigurace nezávislé objekty.  
  
-   Objekty automatizace projektu.  
  
-   Projekt automatizace vlastnost kolekce.  
  
 Další informace o rozšíření pomocí projektu podtypů najdete v tématu [vlastnosti a metody prodloužena projektu podtypů](../../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md).  
  
##### <a name="policy-files"></a>Soubory zásad  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Prostředí poskytuje příklad rozšíření systému projektu základní se podtypem projektu v jeho implementaci zásad souborů. Soubor zásad umožňuje shaping z [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí pomocí funkce, které zahrnují Průzkumníku řešení správy **přidat projekt** dialogové okno, **přidat novou položku** dialogové okno a  **Vlastnosti** dialogové okno. Podtyp zásady přepíše a rozšiřuje tyto funkce prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg>, `IOleCommandTarget` a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> implementace.  
  
##### <a name="aggregation-mechanism"></a>Mechanismus agregace  
 V prostředí projektu dílčí agregace mechanismus podporuje více úrovní agregace, což umožňuje podtypem pokročilé provádí další flavoring podporu projektu. Také pomocné objekty projektu podtypu, jako například <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg>, jsou navržené tak, aby více úrovní rozvrstvení. V souladu s omezeními COM a COM pravidla agregace, podtypů projektu a základní projekty muset být naprogramovaný spolupráce při tak aby vnitřní dílčí nebo základní projekt správně zapojit se do delegování volání metod a správu počty odkazů . To znamená projektu chystáte agregovat musí být naprogramovaný tak, aby podporu agregace.  
  
 Následující obrázek znázorňuje schématem agregace dílčí víceúrovňovou projektu.  
  
 ![Visual Studio víceúrovňové projectflavor grafika](../../extensibility/internals/media/vs_multilevelprojectflavor.gif "VS_MultilevelProjectFlavor")  
Podtyp víceúrovňové projektu  
  
 Podtypem agregace víceúrovňovou projektu se skládá ze tří úrovní základní projektu, který je agregaci podtypem projektu a pak další agregaci podtypem pokročilé projektu. Obrázek se zaměřuje na některé podpůrné rozhraní, které jsou k dispozici jako součást [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projektu dílčí architektura.  
  
##### <a name="deployment-mechanisms"></a>Mechanismy nasazení  
 Mezi mnoha systému základní projektu jsou funkce vylepšit určením podtypem projektu nasazení mechanismy. Podtyp projekt vliv nasazení mechanismy implementací rozhraní pro konfiguraci (například <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg>), se načítají pomocí volání QueryInterface na <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfgProvider>. Ve scénáři, kde dílčí projektu a dílčí pokročilé projektu přidejte jinou konfiguraci implementace, základní projekt volá `QueryInterface` na dílčí pokročilé projektu `IUnknown`. Pokud dílčí vnitřní projekt obsahuje implementace konfigurace, který základní projekt se žádostí o pokročilé projektu dílčí delegáty pro implementaci poskytované dílčí vnitřní projektu. Jako mechanismus pro zachování stavu z úrovně jeden agregace, všechny úrovně projektu podtypů implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> udržení bez sestavení související XML data do souborů projektu. Další informace najdete v tématu [uchování dat v souboru projektu nástroje MSBuild](../../extensibility/internals/persisting-data-in-the-msbuild-project-file.md). <xref:EnvDTE80.IInternalExtenderProvider> je implementovaný jako mechanismus pro načtení automatizace Extender z podtypů projektu.  
  
 Na následujícím obrázku se zaměřuje na implementace rozšiřujícího objektu automatizace, procházet objekt konfigurace projektu na konkrétní používané podtypů projektu rozšíření systému základní projektu.  
  
 ![Obrázek Automatické rozšíření příchuť projektu VS](../../extensibility/internals/media/vs_projectflavorautoextender.gif "VS_ProjectFlavorAutoExtender")  
Projekt dílčí automatizace rozšiřujícího objektu.  
  
 Podtypů projektu můžete rozšířit systému základní projektu tím, že rozšíří objektový model automatizace. Tyto jsou definované jako součást objekt automatizace DTE a slouží k rozšíření objekt projektu `ProjectItem` objektu a `Configuration` objektu. Další informace najdete v tématu [rozšíření objektový Model projektu základní](../../extensibility/internals/extending-the-object-model-of-the-base-project.md).  
  
## <a name="multi-level-aggregation"></a>Víceúrovňovou agregace  
 Implementace dílčí projektu, který zabalí nižší úrovně projektu podtypem potřeba naprogramovat tak spolupráce při umožňující dílčí vnitřní projektu fungovat správně. Seznam programování odpovědnosti zahrnuje:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> Implementace dílčí projekt, který zahrnuje vnitřní dílčí musí delegovat na <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> implementace dílčí vnitřní projektu pro obě <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.Load%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.Save%2A> metody.  
  
-   <xref:EnvDTE80.IInternalExtenderProvider> Implementace dílčí projektu obálku musí delegovat na u jeho dílčí vnitřní projektu. Konkrétně, provádění <xref:EnvDTE80.IInternalExtenderProvider.GetExtenderNames%2A> musí získat řetězec názvů z dílčí vnitřní projektu a pak zřetězení řetězců chce přidat jako Extender.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfgProvider> Implementace projektu podtypu obálku musí vytvořit instanci <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg> objekt jeho vnitřní projektu dílčí a po dobu jako soukromý delegát, protože jen přímo zná objekt konfigurace projektu základní projekt, který obálku objekt konfigurace dílčí projektu existuje. Dílčí vnější projektu můžete zpočátku zvolte konfigurace rozhraní, které chce zpracovat přímo a následně delegovat zbytek na dílčí vnitřní projektu implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg.get_CfgType%2A>.  
  
## <a name="supporting-interfaces"></a>Podpora rozhraní  
 Základní projekt deleguje volání podpory rozhraní přidal projektu podtypem, rozšířit různé aspekty jeho implementace. To zahrnuje rozšíření objektů konfigurace projektu a různé objekty prohlížeče vlastnost. Tato rozhraní se načítají pomocí volání `QueryInterface` na `punkOuter` (ukazatel `IUnknown`) z agregátoru dílčí nejkrajnější projektu.  
  
|Rozhraní|Podtyp projektu|  
|---------------|---------------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfg>|Umožňuje dílčí projektu na:<br /><br /> -Zadejte implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg>.<br />-Řízení spuštění ladicího programu tím, že dílčí projektu zajistit jejich vlastní implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>.<br />-Zakažte vyhodnocení výrazu při návrhu tak, že správně zpracování `DBGLAUNCH_DesignTimeExprEval` případu při implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.QueryDebugLaunch%2A>.|  
|<xref:EnvDTE80.IInternalExtenderProvider>|Umožňuje dílčí projektu na:<br /><br /> -Rozšířit <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> projektu přidat nebo odebrat nezávislé vlastnosti konfigurace projektu.<br />-Rozšířit objekt automatizace projektu (<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>) projektu.<br /><br /> Výše uvedené hodnoty vlastností jsou převzaty z <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> výčtu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>|Umožňuje dílčí projektu pro mapování zpět do <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg> objekt daný objekt procházet konfigurace projektu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBrowseObject>|Umožňuje dílčí projektu pro mapování zpět do <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> nebo `VSITEMID` objekt, zadaný objekt procházet konfigurace projektu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment>|Umožňuje dílčí projektu uchovávat libovolné XML strukturovaná data do souboru projektu (.vbproj nebo .csproj). Tato data nejsou viditelné pro MSBuild.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>|Umožňuje dílčí projektu na:<br /><br /> -Přidáte nové vlastnosti nástroje MSBuild natrvalo.<br />-Odebrání nepotřebných vlastnosti nástroje MSBuild.<br />-Dotaz na aktuální hodnota vlastnosti nástroje MSBuild.<br />-Změňte aktuální hodnotu vlastnosti nástroje MSBuild.|  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID2>