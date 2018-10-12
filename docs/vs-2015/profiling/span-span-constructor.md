---
title: span::span – konstruktor | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::span::span
helpviewer_keywords:
- Concurrency::diagnostic::span constructor
ms.assetid: 8b5578aa-5e5c-4ac7-87c7-ce87c4246e2c
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 21c47e968aa4e762c71a60d5c8bfc1700bffb30b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49256006"
---
# <a name="spanspan-constructor"></a>span::span – konstruktor
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Inicializuje novou instanci třídy `span` třídy.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
span(  
   const marker_series& _Series,  
   _In_ LPCTSTR _Format,  
   ...  
);  
span(  
   const marker_series& _Series,  
   marker_importance _Importance,  
   _In_ LPCTSTR _Format,  
   ...  
);  
span(  
   const marker_series& _Series,  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
span(  
   const marker_series& _Series,  
   marker_importance _Importance,  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `_Series`  
 Platné značky řady kontextu.  
  
 `_Format`  
 Složený řetězec formátu, který obsahuje textu smíšeného s nula nebo více položek formátu, který odpovídá objektům v seznamu argumentů.  
  
 `_Importance`  
 Úroveň důležitosti.  
  
 `_Category`  
 Kategorie.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkersobj.h  
  
 **Namespace:** Concurrency::Diagnostic –
 
 ## <a name="see-also"></a>Viz také
 [span – třída](../profiling/span-class.md)



