---
title: "&lt;RelatedProducts&gt; prvek (zavaděče) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MSBuild.GenerateBootstrapper.MissingDependency
- MSBuild.GenerateBootstrapper.DuplicateItems
- MSBuild.GenerateBootstrapper.IncludedProductIncluded
- MSBuild.GenerateBootstrapper.DependencyNotFound
- MSBuild.GenerateBootstrapper.PackageFileNotFound
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <RelatedProducts> element [bootstrapper]
ms.assetid: bf152712-4c1e-48bd-9b7f-311cf0fdb832
caps.latest.revision: 
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 548c1002eae581dc0e231f8dd2e28ee4a8376e27
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltrelatedproductsgt-element-bootstrapper"></a>&lt;RelatedProducts&gt; – Element (zaváděcího nástroje)
`RelatedProducts` Element definuje jiné produkty, které závisí na nebo jsou součástí aktuální produkt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<RelatedProducts>  
    <DependsOnProduct  
        Code  
    />  
    <EitherProducts>  
        <DependsOnProduct  
            Code  
        />  
    </EitherProducts>  
    <IncludesProduct  
        Code  
    />  
</RelatedProducts>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `RelatedProducts` Element je podřízená `Product` elementu. Nemá žádné atributy.  
  
## <a name="dependsonproduct"></a>DependsOnProduct  
 `DependsOnProduct` Prvek označuje, že aktuální produkt závisí na s názvem produktu a uvedený produkt by měl být nainstalovaný před tímto aktuálním. Je podřízená `RelatedProducts` elementu. A `RelatedProducts` element může mít jeden nebo více `DependsOnProduct` elementy.  
  
 `DependsOnProduct`má následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Code`|Název kódu součástí produktu podle specifikace `ProductCode` atribut `Product` elementu. Další informace najdete v tématu [ \<produktu > Element](../deployment/product-element-bootstrapper.md).|  
  
## <a name="eitherproducts"></a>EitherProducts  
 `EitherProducts` Element definuje nula nebo více `DependsOnProduct` prvky, a nemá žádné atributy. Alespoň jeden `DependsOnProduct` v této sadě musí být nainstalována před aktuální produkt. A `RelatedProducts` element může obsahovat nula nebo více `EitherProducts` elementy.  
  
## <a name="includesproduct"></a>IncludesProduct  
 `IncludesProduct` Element označuje, že je obsažen v aktuální instalaci produktu a nevyžaduje samostatnou instalaci. Je podřízená `RelatedProducts` elementu. A `RelatedProducts` element může mít jeden nebo více `IncludesProduct` elementy.  
  
 `IncludesProduct`má následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Code`|Název kódu součástí produktu podle specifikace `ProductCode` atribut `Product` elementu. Další informace najdete v tématu [ \<produktu > Element](../deployment/product-element-bootstrapper.md).|  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu určuje, že Microsoft Installer je instalován s [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]a proto nebude potřebovat samostatnou instalaci.  
  
```  
<RelatedProducts>  
    <IncludesProduct Code="Microsoft.Windows.Installer.2.0" />  
</RelatedProducts>  
```  
  
## <a name="see-also"></a>Viz také  
 [\<Produkt > elementu](../deployment/product-element-bootstrapper.md)