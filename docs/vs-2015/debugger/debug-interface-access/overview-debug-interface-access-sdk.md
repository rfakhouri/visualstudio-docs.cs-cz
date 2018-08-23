---
title: Přehled (přístup k rozhraní ladění SDK) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- user-defined types
- .dbg files
- modules
- interfaces [DIA SDK]
- DBG files
- procedures [DIA SDK]
- executable files
- COM objects, in DIA SDK
- compilands
- executable images
ms.assetid: 720b4479-a8bc-4fec-860e-80c1a0780405
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8de5b25b1ece8c4523ba222a97f1107d2275ba3a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666997"
---
# <a name="overview-debug-interface-access-sdk"></a>Přehled (Přístup k rozhraní ladění SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [přehled (Debug Interface Access SDK)](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/overview-debug-interface-access-sdk).  
  
Použijte DIA SDK pro přístup k Microsoft ladicí informace. DIA SDK poskytuje že com na základě sada rozhraní API, která eliminuje potřebu revize kódu pokaždé, když se změní formát ladicích informací společnosti Microsoft. DIA SDK také umožňuje čtení z vybrané sady z předchozí verze informací o ladění, umístěn v souborech PDB a dbg generovaných [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] verze 5.0 a novější.  
  
 Každé rozhraní v sadě DIA SDK představuje jiný objekt modelu COM, s výjimkou, je-li uvedeno jinak. Další rozhraní a tedy další objekty, jsou vytvořeny pomocí explicitní dotazů, jako například [idiadatasource::opensession –](../../debugger/debug-interface-access/idiadatasource-opensession.md) nebo [idiasession::findchildren –](../../debugger/debug-interface-access/idiasession-findchildren.md), nikoli voláním `QueryInterface` na existující ukazatele rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Idiadatasource::opensession –](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)



