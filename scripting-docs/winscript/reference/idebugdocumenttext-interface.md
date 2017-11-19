---
title: "Idebugdocumenttext – rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IDebugDocumentText interface
ms.assetid: 242bad79-9c0a-4a30-879a-9f43db4e022b
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9522d1075cd796fb69f6abbc42adc2706a817fed
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenttext-interface"></a>IDebugDocumentText – rozhraní
Poskytuje přístup k verzi dokumentu ladění prostého textu. Toto rozhraní používá následující konvence:  
  
-   Pozice znaku a čísla řádků jsou od nuly.  
  
-   Umístění znaku představují znak odsazení; nevytvářejí představují bajtů ani odsazení aplikace word. Pro Win32 je pozice znaku posun kódování Unicode.  
  
 Kromě metod zděděno z `IDebugDocument`, `IDebugDocumentText` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugDocumentText::GetDocumentAttributes](../../winscript/reference/idebugdocumenttext-getdocumentattributes.md)|Vrací atributy dokumentu.|  
|[IDebugDocumentText::GetSize](../../winscript/reference/idebugdocumenttext-getsize.md)|Vrátí počet řádků a počet znaků v dokumentu.|  
|[IDebugDocumentText::GetPositionOfLine](../../winscript/reference/idebugdocumenttext-getpositionofline.md)|Vrátí pozice znaku odpovídající prvnímu znaku řádku.|  
|[IDebugDocumentText::GetLineOfPosition](../../winscript/reference/idebugdocumenttext-getlineofposition.md)|Vrátí číslo řádku a volitelně odsazení znaku v rámci řádku, která odpovídá dané pozice znaku.|  
|[IDebugDocumentText::GetText](../../winscript/reference/idebugdocumenttext-gettext.md)|Načte znaky nebo znak atributy přidružené rozsah pozice znaku.|  
|[IDebugDocumentText::GetPositionOfContext](../../winscript/reference/idebugdocumenttext-getpositionofcontext.md)|Vrátí pozice znaku rozsahu odpovídající kontextu dokumentu.|  
|[IDebugDocumentText::GetContextOfPosition](../../winscript/reference/idebugdocumenttext-getcontextofposition.md)|Vytvoří objekt kontextu dokumentu odpovídající rozsah pozici zadaný znak.|