---
title: "Chyba: Nelze se připojit k počítači &lt;název&gt;. Počítač nebyl nalezen v síti. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.remote.dcom_disabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- DCOM, unable to connect error
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e8b7ef99717f0a68fbd17245958840c89cdf8544
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="error-unable-to-connect-to-the-machine-ltnamegt-the-machine-cannot-be-found-on-the-network"></a>Chyba: Nelze se připojit k počítači &lt;název&gt;. Počítač nebyl nalezen v síti.
K tomuto chování dochází, pokud platí jedna z následujících podmínek:  
  
-   Připojení ke vzdálenému počítači bylo přerušeno.  
  
-   Váš uživatelský účet na vzdáleném počítači, je zakázán.  
  
-   Vypršela platnost hesla na vzdáleném počítači.  
  
### <a name="to-resolve-this-behavior"></a>Chcete-li toto chování  
  
-   Ujistěte se, že místní počítač a vzdáleného počítače jsou ve stejné síti. K tomu použijte Průzkumník systému Microsoft Windows (nebo Průzkumníka souborů) a zkuste to pro přístup ke vzdálenému počítači.  
  
     – a –  
  
-   Ujistěte se, že je povolena uživatelský účet, který používáte pro připojení ke vzdálenému počítači.  
  
     – a –  
  
-   Ujistěte se, zda je heslo, které používáte pro připojení ke vzdálenému počítači platný a zda nevypršela platnost.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)   
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)