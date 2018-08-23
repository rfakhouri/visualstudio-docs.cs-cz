---
title: Zásady šablon a okno Vlastnosti | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Properties window, template policy
ms.assetid: 1d8019d3-5e57-47ba-b358-526b0796a63b
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9f8b2085818c539fe0e751a63562496363b43555
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676295"
---
# <a name="template-policy-and-the-properties-window"></a>Zásady šablon a okno Vlastnosti
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [zásady šablon a okno Vlastnosti](https://docs.microsoft.com/visualstudio/extensibility/internals/template-policy-and-the-properties-window).  
  
Pokud projekt je obsažena v šabloně projektu organizace, je tento projekt šablony organizace vynucovat zásady. Šablony zásad stane omezující systému, který je možné nastavit výchozí hodnoty pro vlastnosti, skrýt vlastnosti, přidat vlastnosti a tak dále.  
  
 Pomocí zásad šablony pro ovládací prvek zobrazení informací v **vlastnosti** okna se liší od implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> zpracovává vlastnosti objektu na úrovni součásti šablony zásad slouží k omezení vlastností objektu na úrovni řešení nebo projektu. Jinými slovy  
  
-   Implementace metody na <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> k určení, co se zobrazí **vlastnosti** okna pro příslušné objekty  
  
-   Použít šablonu zásad na úrovni řešení a projektu k určení, co se zobrazí **vlastnosti** okně dříve zadané objekty  
  
 Pomocí zásad šablony pro specifické vlastnosti v selektivně omezit **vlastnosti** okno při zadaného typu položky projektu je vybrán v **Průzkumníku řešení** může být výhodný pro všechny členy Vývojový tým práci na projektu. Například pomocí šablony zásad, můžete nastavit všechny připojovací řetězec informace v databázi pro vývojáře, kteří a nastavte připojovací řetězec jen pro čtení. Tímto způsobem můžete zadat jednoduchý způsob, jak zajistit, že každý vývojář používá správnou cestu pro přístup k datům.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>   
 [Rozšíření vlastností](../../extensibility/internals/extending-properties.md)

