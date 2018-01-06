---
title: "Přehled (přístup k rozhraní ladění SDK) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cb13b9a77bcd34b22a7a82182a63440cb02a4e76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="overview-debug-interface-access-sdk"></a>Přehled (Přístup k rozhraní ladění SDK)
Použijte pro přístup k informacím ladění Microsoft DIA SDK. DIA SDK poskytuje že com na základě sada rozhraní API, která eliminuje nutnost přepisu kódu při každé změně formát ladicích informací společnosti Microsoft. DIA SDK vám umožní číst z vyberte sadu předchozích verzích informace o ladění, umístěný v PDB a dbg soubory generované [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] verze 5.0 a novější.  
  
 Každé rozhraní v sadě DIA SDK představuje jiný objekt COM, s výjimkou, kde je uvedeno jinak. Další rozhraní a proto další objekty, jsou vytvořeny pomocí explicitní dotazy, jako například [idiadatasource::opensession –](../../debugger/debug-interface-access/idiadatasource-opensession.md) nebo [idiasession::findchildren –](../../debugger/debug-interface-access/idiasession-findchildren.md), nikoli voláním `QueryInterface` na existující ukazatele rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Idiadatasource::opensession –](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)