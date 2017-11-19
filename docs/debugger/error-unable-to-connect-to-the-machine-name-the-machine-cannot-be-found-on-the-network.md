---
title: "Chyba: Nelze se připojit k počítači &lt;název&gt;. Počítač nebyl nalezen v síti. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.remote.dcom_disabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: DCOM, unable to connect error
ms.assetid: b584b5db-ef52-45ed-8561-1314da3cc5b8
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e8ed30ca3baeb29f92c4d5f02b64c581ef9a37a7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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