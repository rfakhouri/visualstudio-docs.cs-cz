---
title: "Automatické formátování ve službě jazyk starší | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f09ab8a948011cdc53516ec21f0d213852166956
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>Automatické formátování ve službě jazyk starší verze
Pomocí automatického formátování, služba jazyka automaticky vloží fragment kódu, když uživatel zahájí na typ konstrukce známé kódu.  
  
## <a name="automatic-formatting-behavior"></a>Automatické formátování chování  
 Například když zadáte `if`, služba jazyka automaticky vloží odpovídající složené závorky, nebo když stisknete klávesu ENTER, služba jazyka vynutí kurzor na novém řádku na úroveň odpovídající odsazení, podle toho, jestli předchozím Otevře se nový obor řádku.  
  
 Příkaz filtr použít pro zbytek služba jazyka lze také pro automatické formátování. Můžete také zvýraznění odpovídající složené závorky voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj služby jazyk starší verze](../../extensibility/internals/developing-a-legacy-language-service.md)