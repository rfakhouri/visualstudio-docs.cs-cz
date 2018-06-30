---
title: Přehled modelu programování SharePoint rozšíření nástrojů | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Studio, extending tools
- SharePoint development in Visual Studio, extensibility object models
- SharePoint development in Visual Studio, extending tools
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7882439d6c25cf57a435e4bbe046b2121c3e0405
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120196"
---
# <a name="overview-of-the-programming-model-of-sharepoint-tools-extensions"></a>Přehled modelu programování služby SharePoint rozšíření nástrojů
  Při vytváření rozšíření pro nástroje služby SharePoint v sadě Visual Studio, můžete začít tím, že implementujete jeden nebo více rozhraní rozšíření, které jsou vystavené nástroje služby SharePoint. Ve většině případů budete implementovat funkce v rozšíření také používat jiné typy poskytované nástroje služby SharePoint. V některých případech můžete také použít typy v jiných objektové modely poskytované sadě Visual Studio a služby SharePoint. Musíte pochopit účel každé z těchto objektových modelů a vědět, jak je používat spolu vzájemně vytvoření rozšíření pro nástroje služby SharePoint.  
  
## <a name="extend-the-sharepoint-tools-by-implementing-extensibility-interfaces"></a>Rozšíření nástrojů SharePoint implementací rozhraní rozšíření
 Visual Studio použije Managed Extensibility Framework (MEF) v rozhraní .NET Framework 4 zajistit model rozšiřitelnosti pro nástroje služby SharePoint. MEF je rozhraní API (implementována v sestavení System.ComponentModel.Composition), umožňuje aplikacím vystavit body rozšiřitelnosti a zjišťovat a načíst rozšíření za běhu. Další informace o rozhraní MEF najdete v tématu [spravované rozhraní rozšiřitelnosti &#40;MEF&#41;](/dotnet/framework/mef/index).  
  
 K rozšíření nástrojů služby SharePoint, implementujte jednu nebo více rozhraní rozšíření, zpřístupněných Visual Studio. Musíte také použít <xref:System.ComponentModel.Composition.ExportAttribute>, a další služby SharePoint nástroje specifické atributy jako nezbytné, aby se vaší implementace rozhraní. Následující tabulka uvádí rozhraní, které můžete implementovat, abyste rozšíření nástrojů služby SharePoint.  
  
|Rozhraní|Popis|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider>|Implementace tohoto rozhraní můžete definovat nový typ položky projektu služby SharePoint. Příklad, naleznete v části [postupy: definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension>|Implementace tohoto rozhraní pro rozšíření typu položky projektu služby SharePoint, který už je nainstalovaný v sadě Visual Studio. Příklad, naleznete v části [postupy: vytváření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension>|Implementace tohoto rozhraní pro rozšíření projektů služby SharePoint. Příklad, naleznete v části [postupy: vytváření rozšíření projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep>|Implementace tohoto rozhraní můžete definovat nový krok nasazení, které mohou být provedeny, když je položka projektu služby SharePoint nasazen nebo stažen. Příklad, naleznete v části [návod: vytvoření vlastního kroku nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension>|Implementace tohoto rozhraní rozšířit stávající uzel v části **připojení služby SharePoint** uzlu **Průzkumníka serveru** okno. Příklad, naleznete v části [postupy: rozšíření uzlu služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider>|Implementace tohoto rozhraní můžete definovat nový typ pod uzlem **připojení služby SharePoint** uzel v **Průzkumníka serveru** okno. Příklad, naleznete v části [postupy: rozšíření uzlu služby SharePoint v Průzkumníku serveru](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule>|Implementace tohoto rozhraní můžete definovat vlastní funkci pravidla ověřování. Příklad, naleznete v části [postupy: vytvoření vlastní funkce a balíček ověřovacích pravidel pro řešení služby SharePoint](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule>|Implementace tohoto rozhraní můžete definovat vlastní balíček ověřovacího pravidla. Příklad, naleznete v části [postupy: vytvoření vlastní funkce a balíček ověřovacích pravidel pro řešení služby SharePoint](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).|  
  
 Po implementaci rozšíření nástrojů služby SharePoint, je nutné nasadit sestavení rozšíření v sadě Visual Studio balíčku rozšíření (VSIX) Chcete-li povolit chcete zjišťovat a načíst rozšíření Visual Studio. Další informace najdete v tématu [nasadit rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="understand-the-object-models-that-you-use-in-sharepoint-tools-extensions"></a>Pochopení objektové modely, které používáte v rozšíření nástrojů SharePoint
 Existuje několik objektové modely, které můžete použít při vytváření rozšíření pro nástroje služby SharePoint:  
  
-   *Nástroje služby SharePoint objektu modelu*. Tento objektový model poskytuje rozhraní rozšíření, které můžete implementovat pro vytvoření rozšíření nástrojů služby SharePoint a další související typy.  
  
-   *Visual Studio automatizace a integrace objektové modely*. Pomocí těchto modelů objektu pro přístup k sadě Visual Studio funkce, které jsou nad rámec objektový model nástrojů služby SharePoint.  
  
    > [!NOTE]  
    >  Můžete převést některé objekty v modelu objektu nástroje SharePoint na objekty v sadě Visual Studio automatizace a integrace objektové modely a naopak a pomocí projektu služby SharePoint. Další informace najdete v tématu [převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md).  
  
-   *Objektové modely SharePoint serveru a klienta*. Pomocí těchto modelů objektu upravit web služby SharePoint nebo k načtení dat z webu služby SharePoint v kontextu rozšíření nástrojů SharePoint.  
  
### <a name="sharepoint-tools-object-model"></a>Objektový model nástrojů služby SharePoint
 Každé rozšíření nástrojů SharePoint používá typy v modelu objektu nástrojů služby SharePoint k definování chování jádra a funkce rozšíření. Následující tabulky popisují obory názvů, které jsou zahrnuty v tomto modelu objektu a sestavení, která je obsahuje.

#### <a name="microsoftvisualstudiosharepointdll"></a>Microsoft.VisualStudio.SharePoint.dll    
|Obor názvů|Popis|  
|-|-|  
|<xref:Microsoft.VisualStudio.SharePoint>|Obsahuje typy, které používáte pro rozšíření a automatizaci systému projektu služby SharePoint. Například můžete rozšířit předdefinovaný projektů služby SharePoint a položky projektu, nebo můžete vytvořit svoje vlastní položky projektu. Další informace najdete v tématu [rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Deployment>|Obsahuje typy, které můžete použít k rozšíření procesu nasazení pro projekty SharePoint, jako je například vytváření kroky nasazení a konfigurace nasazení. Další informace najdete v tématu [balení a nasazení SharePoint rozšířit](../sharepoint/extending-sharepoint-packaging-and-deployment.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Explorer>|Obsahuje typy, které můžete použít k rozšíření uzly v rámci **připojení služby SharePoint** uzlu **Průzkumníka serveru** okno, nebo k definování nových typů uzlů. Další informace najdete v tématu [rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Features>|Obsahuje typy, které používáte pro přístup k definice funkce v projektu služby SharePoint.|  
|<xref:Microsoft.VisualStudio.SharePoint.Packages>|Obsahuje typy, které používáte pro přístup k definici balíčku v řešení služby SharePoint.|  
|<xref:Microsoft.VisualStudio.SharePoint.Validation>|Obsahuje typy, které můžete použít k přizpůsobení chování funkce a balíku ověření pro projekty SharePoint. Další informace najdete v tématu [postupy: vytvoření vlastní funkce a balíček ověřovacích pravidel pro řešení služby SharePoint](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).| 

#### <a name="microsoftvisualstudiosharepointcommandsdll"></a>Microsoft.VisualStudio.SharePoint.Commands.dll
|Obor názvů|Popis|  
|-|-|  
|<xref:Microsoft.VisualStudio.SharePoint.Commands>|Obsahuje typy, které můžete použít k vytvoření vlastních *SharePoint – příkazy*. Příkaz SharePoint je metoda, která volá do objektový model serveru SharePoint z rozšíření nástrojů služby SharePoint. Další informace najdete v tématu [volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md).|

#### <a name="microsoftvisualstudiosharepointexplorerextensionsdll"></a>Microsoft.VisualStudio.SharePoint.Explorer.Extensions.dll
|Obor názvů|Popis|  
|-|-| 
|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions>|Obsahuje typy, které vám pomůže získat informace o předdefinovaných **Průzkumníka serveru** uzlů, které představují jednotlivé součásti na webu služby SharePoint, jako je například uzel, který představuje seznam, pole nebo typ obsahu. Další informace najdete v tématu [rozšíření uzlu připojení služby SharePoint v Průzkumníku serveru](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).|  
  
### <a name="visual-studio-automation-object-model"></a>Objektový model sady Visual Studio automatizace
 Objektový model automatizace sady Visual Studio poskytuje rozhraní API, které můžete použít k automatizaci projektů sady Visual Studio a rozhraní IDE. Použijte objektový model sady Visual Studio k provádění úloh souvisejících s projektem, které nejsou specifické pro projekty SharePoint nebo provádět další úlohy obecné automatizace v sadě Visual Studio. Obvyklým tento objektový model se často používá v doplňky sady Visual Studio a makra, ale můžete ji použít i v rozšíření nástrojů služby SharePoint.  
  
 Hlavní část objektový model automatizace sady Visual Studio je definována v *EnvDTE.dll* sestavení. *EnvDTE\\<version>.dll* sestavení poskytují další funkce, která byla zavedena v konkrétních verzí sady Visual Studio. Tyto sestavení jsou zahrnuty v sadě Visual Studio.  
  
 Další informace o modelu objektu automatizace najdete v tématu [referenční informace sady Visual Studio SDK](../extensibility/visual-studio-sdk-reference.md).  
  
### <a name="visual-studio-integration-object-model"></a>Objektový model sady Visual Studio integrace
 Objektový model integrace poskytuje rozhraní API, které můžete použít pro přidání funkcí do sady Visual Studio tak, že vytvoříte *VSPackage*. VSPackage je modul, který rozšiřuje Visual Studio IDE nabízí vlastní funkce, jako jsou nástroje systému windows, editory, návrhářů, služby a projekty.  
  
 Pokud chcete přidat nové funkce sady Visual Studio, který se použije s integrovanou nástroje služby SharePoint, můžete použít objektový model integrace. Například pokud vytvoříte vlastní položky projektu služby SharePoint, který představuje vlastní akce pro web služby SharePoint, můžete také vytvořit VSPackage implementující návrháře pro vlastní akci. Můžete přidružit návrháře vlastní akce přidáním položky místní nabídky do položky projektu, který představuje vlastní akce v **Průzkumníku řešení**. Vaše designer můžete otevřít tak, že otevřete jeho místní nabídky (buď kliknutím pravým tlačítkem vlastní položky projektu akce nebo tak, že ho vyberete a pak vyberete **Shift**+**F10** klíče) a pak vyberete **Otevřete**.  
  
 Tento objektový model je definována v sadě sestavení, které jsou součástí sady Visual Studio SDK. Mezi hlavní sestavení v tomto objektu modelu patří *Microsoft.VisualStudio.Shell.11.0.dll*, *Microsoft.VisualStudio.Shell.Interop.dll*, a  *Microsoft.VisualStudio.OLE.Interop.dll*.  
  
 Další informace o modelu objektu integrace najdete v tématu [Přehled automatizace modelu](/visualstudio/extensibility/internals/automation-model-overview) a [referenční informace sady Visual Studio SDK](/visualstudio/extensibility/visual-studio-sdk-reference).  
  
### <a name="sharepoint-object-models"></a>Objektové modely SharePoint
 Rozšíření nástrojů služby SharePoint můžete použít rozhraní API služby SharePoint, chcete-li upravit web služby SharePoint nebo k načtení dat z webu služby SharePoint. [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] a [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] zadejte dva různé objektové modely: objektový model serveru a objektového modelu klienta.  
  
 Můžete použít rozhraní API v objektovém modelu v rozšíření nástrojů SharePoint, ale každý objektový model má některé výhody a nevýhody v kontextu rozšíření nástrojů služby SharePoint. Další informace najdete v tématu [volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
|Objektový model|Popis|  
|------------------|-----------------|  
|Objektový model serveru|Objektový model serveru poskytuje přístup k všechny funkce, která [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] a [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] zpřístupnit prostřednictvím kódu programu. Tento objektový model je určen k použití pomocí řešení služby SharePoint, které běží na serveru SharePoint. Většina tento objektový model je definována v *Microsoft.SharePoint.dll* sestavení. Další informace o objektový model serveru najdete v tématu [pomocí objektového modelu služby SharePoint Foundation na straně serveru](http://go.microsoft.com/fwlink/?LinkId=177796).|  
|Model klientského objektu|Objektový model klienta je podmnožinou objektový model serveru, který umožňuje vzájemnou spolupráci s daty služby SharePoint ze vzdáleného klienta nebo serveru. Je navržená tak, abyste minimalizovali počet zpátečních cest, které musí být provedeny k provádění běžných úloh. Většina objektového modelu klienta je definována v *sestavení Microsoft.SharePoint.Client.dll* a *Microsoft.SharePoint.Client.Runtime.dll* sestavení. Další informace o objektového modelu klienta najdete v tématu [spravovaný objektový Model klienta](http://go.microsoft.com/fwlink/?LinkId=177797).|  
  
## <a name="see-also"></a>Viz také:
 [Rozšíření nástrojů SharePoint v sadě Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [Volání do objektových modelů služby SharePoint](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [Použití služby projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md)  
  
