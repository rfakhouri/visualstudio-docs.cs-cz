---
title: ProjectItem – Element | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectItem element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2768a2e55b3e38158f2ef6b856a653a1a2c12dfa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62562400"
---
# <a name="projectitem-element"></a>ProjectItem – element
  Představuje položku Sharepointového projektu. Tento prvek požadovaný kořenový element z *.spdata* souboru.

## <a name="syntax"></a>Syntaxe

```xml
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
|**DefaultFile**|Volitelné **xs: řetězec** atribut.<br /><br /> Relativní cesta, včetně názvu souboru, které se otevře v editoru sady Visual Studio, když otevřete položku Sharepointového projektu v souboru **Průzkumníka řešení**. Cesta je relativní ve složce, která obsahuje *.spdata* souboru.|
|**FeatureReceiverClass**|Volitelné **xs:string** atribut.<br /><br /> Plně kvalifikovaný název třídy příjemce funkce pro tuto položku Sharepointového projektu. Další informace o funkci příjemci, naleznete v tématu [poskytují informace o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|
|**FeatureReceiverAssembly**|Volitelné **xs:string** atribut.<br /><br /> Určuje plně kvalifikovaný název sestavení, který definuje příjemce funkce pro tuto položku Sharepointového projektu. Další informace o funkci příjemci, naleznete v tématu [poskytují informace o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md). Další informace o plně kvalifikované názvy sestavení naleznete v tématu [názvy sestavení](/dotnet/framework/app-domains/assembly-names).|
|**SupportedTrustLevels**|Volitelné **xs:string** atribut.<br /><br /> Určuje úroveň důvěryhodnosti, která podporuje tuto položku Sharepointového projektu. Tato hodnota může být jedna z následujících řetězců: V izolovaném prostoru, FullTrust, nebo všechny. Hodnota všechny určuje Sandboxed a FullTrust.<br /><br /> Vlastního typu položky projektu SharePoint, odpovídá hodnota tohoto atributu, která přiřadíte hodnotu <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedTrustLevels%2A> vlastnost ve vaší implementaci <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metody. Pokud chcete zadat jinou hodnotu pro tento atribut, Visual Studio přepíše hodnotu tak, aby určuje stejnou úroveň důvěryhodnosti, který zadáte <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedTrustLevels%2A> vlastnost.|
|**SupportedDeploymentScopes**|Volitelné **xs:string** atribut.<br /><br /> Určuje oborů nasazení, které podporuje tuto položku Sharepointového projektu. Tato hodnota je řetězec oddělených čárkami, který obsahuje jeden nebo více z následujících řetězců: Farmy, server, Web, webovou aplikaci nebo balíčku. Příklad: `Web, Site`<br /><br /> Vlastního typu položky projektu SharePoint, odpovídá hodnota tohoto atributu, která přiřadíte hodnotu <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedDeploymentScopes%2A> vlastnost ve vaší implementaci <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metody. Pokud chcete zadat jinou hodnotu pro tento atribut, Visual Studio přepíše hodnotu tak, aby určuje stejnou úroveň důvěryhodnosti, který zadáte <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedDeploymentScopes%2A> vlastnost.|
|**Typ**|Vyžaduje **xs:string** atribut.<br /><br /> Identifikátor pro položku Sharepointového projektu. Identifikátor vlastního typu položky projektu SharePoint, je řetězec, který můžete předat <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. Další informace najdete v tématu [jak: Definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).<br /><br /> Seznam identifikátorů pro integrované položek projektu služby SharePoint součástí sady Visual Studio najdete v tématu [položek projektu služby SharePoint rozšiřte](../sharepoint/extending-sharepoint-project-items.md).|

### <a name="child-elements"></a>Podřízené prvky

|Prvek|Popis|
|-------------|-----------------|
|[ExtensionData](../sharepoint/extensiondata-element.md)|Volitelný element.<br /><br /> Představuje kolekci vlastních datových položek, které jsou spojeny s položku Sharepointového projektu.<br /><br /> Může obsahovat pouze jednu **ExtensionData** elementu.|
|[FeatureProperties](../sharepoint/featureproperties-element.md)|Volitelný element.<br /><br /> Reprezentuje kolekci hodnot vlastností, které jsou součástí funkce, když se nasadí do služby SharePoint.<br /><br /> Může obsahovat pouze jednu **FeatureProperties** elementu.|
|[Soubory](../sharepoint/files-element.md)|Volitelné **FileCollectionType** elementu.<br /><br /> Určuje soubory, které chcete nasadit položky projektu služby SharePoint, jako je například souborů elementu funkce a výstupu závislé jiné-projektů služby SharePoint.<br /><br /> Zahrňte **soubory** nebo **ProjectItemFolder** elementu, ale ne obojí.|
|[ProjectItemFolder](../sharepoint/projectitemfolder-element.md)|Volitelné **ProjectItemFolderType** elementu.<br /><br /> Představuje mapované složky.<br /><br /> Zahrňte **soubory** nebo **ProjectItemFolder** elementu, ale ne obojí.|
|[SafeControls –](../sharepoint/safecontrols-element.md)|Volitelný element.<br /><br /> Představuje kolekci ovládacích prvcích ASPX a webových částech, které jsou označeny jako bezpečné pro všechny uživatele pro přístup na libovolné stránce ASPX na webu služby SharePoint.<br /><br /> Může obsahovat pouze jednu **SafeControls** elementu.|

### <a name="parent-elements"></a>Nadřazené prvky
 Žádné

## <a name="element-information"></a>Informace o elementu

|||
|-|-|
|**Namespace**|http:\/\/schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|
|**Název schématu**|Schéma položky projektu služby SharePoint|
|**Soubor ověření**|ProjectItemModelSchema.xsd|
|**Může být prázdný**|Ne|

## <a name="see-also"></a>Viz také:
[Rseference schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)
