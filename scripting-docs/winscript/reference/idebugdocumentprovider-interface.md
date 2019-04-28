---
title: Idebugdocumentprovider – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentProvider interface
ms.assetid: 36510acf-1ef9-479c-a430-d3f09502f82c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5632134c86b5aa0e3cb769a68d2d4cfd944ff35c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63008674"
---
# <a name="idebugdocumentprovider-interface"></a>IDebugDocumentProvider – rozhraní
Poskytuje prostředky pro vytvoření instance dokumentu na vyžádání.  
  
## <a name="remarks"></a>Poznámky  
 To nepřímé znamená, že pro vytvoření instance dokumentu:  
  
- Umožňuje dokumentu, který má načítat, když je to potřeba.  
  
- Umožňuje objektu dokumentu mají být obsažena v rámci ladicího programu integrovaného vývojového prostředí.  
  
- Umožňuje více způsobů, jak přístup na stejný objekt dokumentu.  
  
  To efektivně odděluje od jeho poskytovatele dokumentu a umožňuje poskytovateli provádět další informace o kontextu za běhu.  
  
  Kromě metod zděděných z `IDebugDocumentInfo`, `IDebugDocumentProvider` rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugDocumentProvider::GetDocument](../../winscript/reference/idebugdocumentprovider-getdocument.md)|Způsobí, že dokument, který má být vytvořena, pokud ještě neexistuje.|