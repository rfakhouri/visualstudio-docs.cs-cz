---
title: 'Chyba: Nelze se připojit k počítači &lt;název&gt;. Počítač se v síti nepodařilo najít. | Dokumenty Microsoft'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.remote.dcom_disabled
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- DCOM, unable to connect error
ms.assetid: b584b5db-ef52-45ed-8561-1314da3cc5b8
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: dd1402a476ce2dceaaaf78580b36db20c3eed24f
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65682561"
---
# <a name="error-unable-to-connect-to-the-machine-ltnamegt-the-machine-cannot-be-found-on-the-network"></a>Chyba: Nelze se připojit k počítači &lt;název&gt;. Počítač se v síti nepodařilo najít.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

K tomuto chování dochází, pokud platí jedna z následujících podmínek:  
  
- Připojení ke vzdálenému počítači bylo přerušeno.  
  
- Váš uživatelský účet na vzdáleném počítači zakázaná.  
  
- Vypršela platnost vašeho hesla na vzdáleném počítači.  
  
### <a name="to-resolve-this-behavior"></a>Chcete-li vyřešit tento problém  
  
- Ujistěte se, že místní počítač, tak vzdálenému počítači jsou ve stejné síti. K tomuto účelu použijte Průzkumník systému Microsoft Windows (nebo Průzkumníka souborů), k akci pro přístup ke vzdálenému počítači.  
  
     – a –  
  
- Ujistěte se, že je povolena uživatelský účet, který používáte pro připojení ke vzdálenému počítači.  
  
     – a –  
  
- Ujistěte se, že heslo, které používáte pro připojení ke vzdálenému počítači je platný a že nevypršela platnost.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení nástroje Remote Tools na zařízení](https://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)   
 [Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)
