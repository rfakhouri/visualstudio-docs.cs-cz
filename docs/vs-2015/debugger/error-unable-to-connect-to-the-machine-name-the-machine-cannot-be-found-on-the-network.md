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
ms.openlocfilehash: 41b1cef49425540980938b4d84a1825c171b271b
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60045691"
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
 [Nastavení nástroje Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)   
 [Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)
