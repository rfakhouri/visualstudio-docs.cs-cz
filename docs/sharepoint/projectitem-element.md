---
title: ProjectItem – Element | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectItem element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ea55cbba9115b88ab9bbf763ec489dce7ad7556e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="projectitem-element"></a>ProjectItem – element
  Představuje položky projektu služby SharePoint. Toto je požadovaný kořenový element .spdata souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ProjectItem DefaultFile = "File that opens in the editor when you open the project item"  
    FeatureReceiverClass = "Class that implements a feature receiver for the project item"  
    FeatureReceiverAssembly = "Assembly that defines a feature receiver for the project item"  
    SupportedTrustLevels = "Trust levels that the project item supports"  
    SupportedDeploymentScopes = "Deployment scopes that the project item supports"  
    Type="Identifier for the project item">  
  <Files>...</Files>  
  <ProjectItemFolder>...</ProjectItemFolder>  
  <SafeControls>...</SafeControls>  
  <FeatureProperties>...</FeatureProperties>  
  <ExtensionData>...</ExtensionData>  
</ProjectItem>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|**DefaultFile**|Volitelné **xs:string** atribut.<br /><br /> Relativní cesta, včetně názvu souboru, soubor, který se otevře v editoru Visual Studio se při otevření položky projektu služby SharePoint v **Průzkumníku řešení**. Cesta je relativní ze složky, která obsahuje soubor .spdata.|  
|**FeatureReceiverClass**|Volitelné **xs:string** atribut.<br /><br /> Plně kvalifikovaný název třídy příjemce funkce pro tuto položku projektu služby SharePoint. Další informace o přijímačů funkce najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|  
|**FeatureReceiverAssembly**|Volitelné **xs:string** atribut.<br /><br /> Určuje plně kvalifikovaný název sestavení, který definuje příjemce funkce pro tuto položku projektu služby SharePoint. Další informace o přijímačů funkce najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md). Další informace o názvech plně kvalifikovaný najdete v tématu [názvy sestavení](/dotnet/framework/app-domains/assembly-names).|  
|**SupportedTrustLevels**|Volitelné **xs:string** atribut.<br /><br /> Určuje úrovně důvěryhodnosti, které podporuje této položky projektu služby SharePoint. Tato hodnota může být jedna z následujících řetězců: v izolovaném prostoru, FullTrust, nebo všechny. Hodnota všechny určuje Sandboxed i FullTrust.<br /><br /> Ve vlastního typu položky projektu SharePoint, odpovídá hodnota tohoto atributu na hodnotu, která přiřadíte <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedTrustLevels%2A> vlastnost vaší implementace <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metoda. Pokud zadáte jinou hodnotu pro tento atribut, Visual Studio přepíše hodnotu tak, aby určuje stejnou úroveň důvěryhodnosti, který určíte v <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedTrustLevels%2A> vlastnost.|  
|**SupportedDeploymentScopes**|Volitelné **xs:string** atribut.<br /><br /> Určuje nasazení obory, které podporuje této položky projektu služby SharePoint. Tato hodnota je řetězec s položkami oddělenými čárkou, který se skládá z nejméně jedna z následujících řetězců: farma, server, Web, webovou aplikaci nebo balíčku. Například "Web, lokality".<br /><br /> Ve vlastního typu položky projektu SharePoint, odpovídá hodnota tohoto atributu na hodnotu, která přiřadíte <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedDeploymentScopes%2A> vlastnost vaší implementace <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metoda. Pokud zadáte jinou hodnotu pro tento atribut, Visual Studio přepíše hodnotu tak, aby určuje stejnou úroveň důvěryhodnosti, který určíte v <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedDeploymentScopes%2A> vlastnost.|  
|**Typ**|Požadované **xs:string** atribut.<br /><br /> Identifikátor položky projektu služby SharePoint. V vlastního typu položky projektu SharePoint, je identifikátor řetězec, který můžete předat <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. Další informace najdete v tématu [postupy: definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).<br /><br /> Seznam identifikátorů pro předdefinované položky projektu služby SharePoint, zahrnutá v sadě Visual Studio najdete v tématu [rozšíření položky projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[ExtensionData –](../sharepoint/extensiondata-element.md)|Volitelný element.<br /><br /> Představuje kolekci vlastních datových položek, které jsou přidružené položky projektu služby SharePoint.<br /><br /> Může obsahovat pouze jednu **ExtensionData –** elementu.|  
|[FeatureProperties –](../sharepoint/featureproperties-element.md)|Volitelný element.<br /><br /> Reprezentuje kolekci hodnot vlastností, které jsou součástí funkce při nasazení do služby SharePoint.<br /><br /> Může obsahovat pouze jednu **FeatureProperties –** elementu.|  
|[Soubory](../sharepoint/files-element.md)|Volitelné **FileCollectionType** element.<br /><br /> Určuje soubory k nasazení s položkou projektu služby SharePoint, jako je například souborů funkcí a výstup závislé jiné-projektů služby SharePoint.<br /><br /> Musí obsahovat buď **soubory** nebo **ProjectItemFolder –** elementu, ale ne obojí.|  
|[ProjectItemFolder –](../sharepoint/projectitemfolder-element.md)|Volitelné **ProjectItemFolderType** element.<br /><br /> Představuje mapované složky.<br /><br /> Musí obsahovat buď **soubory** nebo **ProjectItemFolder –** elementu, ale ne obojí.|  
|[SafeControls –](../sharepoint/safecontrols-element.md)|Volitelný element.<br /><br /> Představuje kolekci ovládacích prvků ASPX a webových částí, které jsou označeny jako bezpečné pro všechny uživatele pro přístup na všechny stránky ASPX na webu služby SharePoint.<br /><br /> Může obsahovat pouze jednu **SafeControls –** elementu.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
 Žádné  
  
## <a name="element-information"></a>Informace o elementu  
  
|||  
|-|-|  
|**obor názvů**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu SharePoint|  
|**Ověření souboru**|ProjectItemModelSchema.xsd|  
|**Nesmí být prázdné**|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu položek projektu SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  