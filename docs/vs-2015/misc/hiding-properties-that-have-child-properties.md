---
title: Skrývání vlastností, které mají podřízené vlastnosti | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- properties [Visual Studio SDK], hiding
- Properties window, hiding properties that have child properties
ms.assetid: 6003607e-fc19-4bf9-a299-9f6adf8e92eb
caps.latest.revision: 13
manager: douge
ms.openlocfilehash: bd340b748311bbb257ed0c4bbfe7b972cbf7beb9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672098"
---
# <a name="hiding-properties-that-have-child-properties"></a>Skrývání vlastností, které mají podřízené vlastnosti
Chcete skrýt vlastnosti, které mají podřízené vlastnosti:  
  
-   Pokud máte vnořených projektů, kde nadřazený projekt programově řídí některé aspekty podřízeného projektu.  
  
-   Pokud používáte ovládací prvek s specializované návrháře a nechcete dávají vývojářům úplný přístup ke všem vlastnostem ovládacího prvku.  
  
-   Pokud máte obor vlastnictví objektu a chcete omezit zobrazení vlastností.  
  
### <a name="to-hide-properties-that-have-child-properties"></a>Skrýt vlastnosti, které mají podřízené vlastnosti  
  
1.  Nastavte `pfDisplay` parametr <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.DisplayChildProperties%2A> k `FALSE`.  
  
2.  Nastavte `pfHide` parametr <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HideProperty%2A> k `TRUE`.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení mřížky okna Vlastnosti](../extensibility/internals/properties-display-grid.md)