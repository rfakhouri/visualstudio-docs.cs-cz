---
title: Automatické formátování ve službě jazyk starší | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e052c62afcf9551cc54373da15071fb3903fe950
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126697"
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>Automatické formátování ve službě jazyk starší verze
Pomocí automatického formátování, služba jazyka automaticky vloží fragment kódu, když uživatel zahájí na typ konstrukce známé kódu.  
  
## <a name="automatic-formatting-behavior"></a>Automatické formátování chování  
 Například když zadáte `if`, služba jazyka automaticky vloží odpovídající složené závorky, nebo když stisknete klávesu ENTER, služba jazyka vynutí kurzor na novém řádku na úroveň odpovídající odsazení, podle toho, jestli předchozím Otevře se nový obor řádku.  
  
 Příkaz filtr použít pro zbytek služba jazyka lze také pro automatické formátování. Můžete také zvýraznění odpovídající složené závorky voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj služby starší verze jazyka](../../extensibility/internals/developing-a-legacy-language-service.md)