---
title: Přehled (přístup k rozhraní ladění SDK) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
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
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7374b03da42e34e8ac3be8c7cc570769d9cfd1ff
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68179201"
---
# <a name="overview-debug-interface-access-sdk"></a>Přehled (Přístup k rozhraní ladění SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Použijte DIA SDK pro přístup k Microsoft ladicí informace. DIA SDK poskytuje že com na základě sada rozhraní API, která eliminuje potřebu revize kódu pokaždé, když se změní formát ladicích informací společnosti Microsoft. DIA SDK také umožňuje čtení z vybrané sady z předchozí verze informací o ladění, umístěn v souborech PDB a dbg generovaných [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] verze 5.0 a novější.  
  
 Každé rozhraní v sadě DIA SDK představuje jiný objekt modelu COM, s výjimkou, je-li uvedeno jinak. Další rozhraní a tedy další objekty, jsou vytvořeny pomocí explicitní dotazů, jako například [idiadatasource::opensession –](../../debugger/debug-interface-access/idiadatasource-opensession.md) nebo [idiasession::findchildren –](../../debugger/debug-interface-access/idiasession-findchildren.md), nikoli voláním `QueryInterface` na existující ukazatele rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Idiadatasource::opensession –](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)
