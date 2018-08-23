---
title: 'Chyba: Nelze se připojit k počítači &lt;název&gt;. Počítač se v síti nepodařilo najít. | Dokumenty Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fbd5299c8bd14581a9228b7aa0491af6455b1fda
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666607"
---
# <a name="error-unable-to-connect-to-the-machine-ltnamegt-the-machine-cannot-be-found-on-the-network"></a>Chyba: Nelze se připojit k počítači &lt;název&gt;. Počítač se v síti nepodařilo najít.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: Nelze se připojit k počítači &lt;název&gt;. Počítač nebyl nalezen v síti. ](https://docs.microsoft.com/visualstudio/debugger/error-unable-to-connect-to-the-machine-name-the-machine-cannot-be-found-on-the-network).  
  
K tomuto chování dochází, pokud platí jedna z následujících podmínek:  
  
-   Připojení ke vzdálenému počítači bylo přerušeno.  
  
-   Váš uživatelský účet na vzdáleném počítači zakázaná.  
  
-   Vypršela platnost vašeho hesla na vzdáleném počítači.  
  
### <a name="to-resolve-this-behavior"></a>Chcete-li vyřešit tento problém  
  
-   Ujistěte se, že místní počítač, tak vzdálenému počítači jsou ve stejné síti. K tomuto účelu použijte Průzkumník systému Microsoft Windows (nebo Průzkumníka souborů), k akci pro přístup ke vzdálenému počítači.  
  
     – a –  
  
-   Ujistěte se, že je povolena uživatelský účet, který používáte pro připojení ke vzdálenému počítači.  
  
     – a –  
  
-   Ujistěte se, že heslo, které používáte pro připojení ke vzdálenému počítači je platný a že nevypršela platnost.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení nástroje Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)   
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)



