---
title: Automatické formátování ve službě starší verze jazyka | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 89345c7cd466211292a21ec4ca99276ebf95d67a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53873545"
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>Automatické formátování ve službě starší verze jazyka
Automatické formátování, služba jazyka automaticky vloží fragment kódu, když uživatel zahájí na typ známé kód konstrukce.  
  
## <a name="automatic-formatting-behavior"></a>Chování automatické formátování  
 Například když zadáte *Pokud*, služba jazyka automaticky vloží odpovídající složené závorky, nebo pokud stisknete klávesu ENTER, služba jazyka vynutí kurzor na nový řádek do úrovně odpovídající odsazení, v závislosti na Určuje, zda na každém řádku vždy otevře nový obor.  
  
 Příkaz Filtr používá pro ostatní služby jazyka je také možné pro automatické formátování. Můžete také zvýraznit odpovídající složené závorky voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>.  
  
## <a name="see-also"></a>Viz také:  
 [Vývoj služby starší verze jazyka](../../extensibility/internals/developing-a-legacy-language-service.md)