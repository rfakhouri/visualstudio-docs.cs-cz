---
title: 'Chyba: Nelze se připojit k počítači &lt;název&gt;. Počítač nebyl nalezen v síti. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cf8716602469eccb40dabda15e91d6198fa9b489
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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