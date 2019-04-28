---
title: Iprovideexpressioncontexts – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IProvideExpressionContexts interface
ms.assetid: e4c70f2c-7d86-4fdc-a1cb-f5a0bb8ed037
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b6ec0d5e17b0d3527252352c2e789adfac4fa859
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63410047"
---
# <a name="iprovideexpressioncontexts-interface"></a>IProvideExpressionContexts – rozhraní
Poskytuje způsob, jak vytvořit výčet výraz kontexty známé určitá komponenta. Toto rozhraní implementují obvykle skriptovací stroje.  
  
 Správce ladění procesu používá toto rozhraní najít všechny globální výraz kontexty přidružené k dané vlákno.  
  
> [!NOTE]
> Toto rozhraní je volat z vlákna, které vás zajímají. Záleží implementátora identifikovat aktuální vlákno a vrátí odpovídající enumerátor.  
  
## <a name="methods"></a>Metody  
 Kromě metod zděděných z `IUnknown`, `IProvideExpressionContexts` rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IProvideExpressionContexts::EnumExpressionContexts](../../winscript/reference/iprovideexpressioncontexts-enumexpressioncontexts.md)|Vrátí enumerátor výraz kontexty platná pro tuto součást.|