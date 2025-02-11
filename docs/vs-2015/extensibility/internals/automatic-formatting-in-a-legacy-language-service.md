---
title: Automatické formátování ve službě starší verze jazyka | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e6183fc47138ebb5108e4fbbd2bfa407e5804a72
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68157272"
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>Automatické formátování ve službě starší verze jazyka
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Automatické formátování, služba jazyka automaticky vloží fragment kódu, když uživatel zahájí na typ známé kód konstrukce.  
  
## <a name="automatic-formatting-behavior"></a>Chování automatické formátování  
 Například když zadáte `if`, služba jazyka automaticky vloží odpovídající složené závorky, nebo pokud stisknete klávesu ENTER, služba jazyka vynutí kurzor na nový řádek do úrovně odpovídající odsazení, podle toho, jestli předchozí řádek se otevře nový obor.  
  
 Příkaz Filtr používá pro ostatní služby jazyka je také možné pro automatické formátování. Můžete také zvýraznit odpovídající složené závorky voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj služby starší verze jazyka](../../extensibility/internals/developing-a-legacy-language-service.md)
