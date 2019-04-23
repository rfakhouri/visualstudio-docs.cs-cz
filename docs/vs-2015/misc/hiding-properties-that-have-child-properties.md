---
title: Skrývání vlastností, které mají podřízené vlastnosti | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- properties [Visual Studio SDK], hiding
- Properties window, hiding properties that have child properties
ms.assetid: 6003607e-fc19-4bf9-a299-9f6adf8e92eb
caps.latest.revision: 13
manager: jillfra
ms.openlocfilehash: 1d20b865c6f07d76320a7df8402810c82869ddfb
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60052360"
---
# <a name="hiding-properties-that-have-child-properties"></a>Skrývání vlastností, které mají podřízené vlastnosti
Chcete skrýt vlastnosti, které mají podřízené vlastnosti:  
  
- Pokud máte vnořených projektů, kde nadřazený projekt programově řídí některé aspekty podřízeného projektu.  
  
- Pokud používáte ovládací prvek s specializované návrháře a nechcete dávají vývojářům úplný přístup ke všem vlastnostem ovládacího prvku.  
  
- Pokud máte obor vlastnictví objektu a chcete omezit zobrazení vlastností.  
  
### <a name="to-hide-properties-that-have-child-properties"></a>Skrýt vlastnosti, které mají podřízené vlastnosti  
  
1. Nastavte `pfDisplay` parametr <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.DisplayChildProperties%2A> k `FALSE`.  
  
2. Nastavte `pfHide` parametr <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HideProperty%2A> k `TRUE`.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení mřížky okna Vlastnosti](../extensibility/internals/properties-display-grid.md)