---
title: Automatické formátování ve službě starší verze jazyka | Dokumentace Microsoftu
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
- language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 46e5f30d01a3063a3683aa3cae4ae1da3e0aa141
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669634"
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>Automatické formátování ve službě starší verze jazyka
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [automatické formátování ve službě starší verze jazyka](https://docs.microsoft.com/visualstudio/extensibility/internals/automatic-formatting-in-a-legacy-language-service).  
  
Automatické formátování, služba jazyka automaticky vloží fragment kódu, když uživatel zahájí na typ známé kód konstrukce.  
  
## <a name="automatic-formatting-behavior"></a>Chování automatické formátování  
 Například když zadáte `if`, služba jazyka automaticky vloží odpovídající složené závorky, nebo pokud stisknete klávesu ENTER, služba jazyka vynutí kurzor na nový řádek do úrovně odpovídající odsazení, podle toho, jestli předchozí řádek se otevře nový obor.  
  
 Příkaz Filtr používá pro ostatní služby jazyka je také možné pro automatické formátování. Můžete také zvýraznit odpovídající složené závorky voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj služby starší verze jazyka](../../extensibility/internals/developing-a-legacy-language-service.md)

