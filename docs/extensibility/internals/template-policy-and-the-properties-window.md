---
title: "Šablony zásad a v okně Vlastnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Properties window, template policy
ms.assetid: 1d8019d3-5e57-47ba-b358-526b0796a63b
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 51735bf0f46e5a1ead6f989a8e75745ebc8e6e35
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="template-policy-and-the-properties-window"></a>Šablony zásad a v okně Vlastnosti
Když na projekt se nachází v projektu šablony organizace, tento projekt šablony enterprise může vynutit zásady. Šablony zásad se změní na omezení systém, který můžete použít k nastavení výchozí hodnoty pro vlastnosti, skrýt vlastnosti, přidávat vlastnosti a tak dále.  
  
 Pomocí šablony zásad pro řízení zobrazení informací v **vlastnosti** okno se liší od implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>šablony zásad slouží k omezení vlastnosti objektu na úrovni řešení nebo produktu project zpracovává vlastnosti objektu na úrovni součásti. Jinými slovy  
  
-   Implementace metody na <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> určit, co se zobrazí v **vlastnosti** okna pro konkrétní objekty  
  
-   Pomocí šablony zásad na úrovni řešení a projektu k určení, co se zobrazí v **vlastnosti** okna pro dříve zadané objekty  
  
 Pomocí šablony zásad selektivně omezit specifické vlastnosti v **vlastnosti** okno při položka projektu zadaného typu je vybraný v **Průzkumníku řešení** může být užitečné pro všechny členy Vývojový tým práci na projektu. Například pomocí šablony zásad, můžete nastavit všechny připojovací řetězec informace v databázi pro vaše vývojáře a ověřte připojovací řetězec jen pro čtení. Tímto způsobem zajistíte, že jednoduchý způsob, jak zajistit, že každý vývojář používá správnou cestu pro přístup k datům.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>   
 [Rozšíření vlastností](../../extensibility/internals/extending-properties.md)