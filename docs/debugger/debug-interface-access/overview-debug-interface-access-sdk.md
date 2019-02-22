---
title: Přehled (přístup k rozhraní ladění SDK) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e459d4429d712a9ca4c245d581c6be3578711cd6
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56616748"
---
# <a name="overview-debug-interface-access-sdk"></a>Přehled (Přístup k rozhraní ladění SDK)
Použijte DIA SDK pro přístup k Microsoft ladicí informace. DIA SDK poskytuje že com na základě sada rozhraní API, která eliminuje potřebu revize kódu pokaždé, když se změní formát ladicích informací společnosti Microsoft. DIA SDK také umožňuje čtení z vybrané sady z předchozí verze informací o ladění, umístěn v souborech PDB a dbg generovaných [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] verze 5.0 a novější.

 Každé rozhraní v sadě DIA SDK představuje jiný objekt modelu COM, s výjimkou, je-li uvedeno jinak. Další rozhraní a tedy další objekty, jsou vytvořeny pomocí explicitní dotazů, jako například [idiadatasource::opensession –](../../debugger/debug-interface-access/idiadatasource-opensession.md) nebo [idiasession::findchildren –](../../debugger/debug-interface-access/idiasession-findchildren.md), nikoli voláním `QueryInterface` na existující ukazatele rozhraní.

## <a name="see-also"></a>Viz také
- [IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)
- [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)