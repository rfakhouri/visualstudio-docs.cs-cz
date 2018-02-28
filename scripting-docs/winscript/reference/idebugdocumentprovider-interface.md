---
title: "Idebugdocumentprovider – rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentProvider interface
ms.assetid: 36510acf-1ef9-479c-a430-d3f09502f82c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 262794718e238068cfd9a8e3fae5161b9fe8cc54
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumentprovider-interface"></a>IDebugDocumentProvider – rozhraní
Poskytuje prostředky pro vytvoření instance dokumentu na vyžádání.  
  
## <a name="remarks"></a>Poznámky  
 To nepřímých znamená pro vytvoření instance dokumentu:  
  
-   Umožňuje dokumentu, který má načíst, když je to potřeba.  
  
-   Umožňuje objekt dokumentu, který má být obsažené v ladicím programu IDE.  
  
-   Umožňuje více způsobů pro přístup na stejný objekt dokumentu.  
  
 To efektivně odděluje dokumentu od jeho zprostředkovatelem a umožňuje poskytovateli k provedení další informace o kontextu spuštění.  
  
 Kromě metod zděděno z `IDebugDocumentInfo`, `IDebugDocumentProvider` rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugDocumentProvider::GetDocument](../../winscript/reference/idebugdocumentprovider-getdocument.md)|Způsobí, že dokumentu, který má být vytvořena instance, pokud ještě neexistuje.|