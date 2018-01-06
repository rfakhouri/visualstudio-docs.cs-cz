---
title: "Chyba: Brány Firewall v místním počítači | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.firewall.localmachine
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 160e71e357046b69019323ada5ff9cde006460bc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="error-firewall-on-local-machine"></a>Chyba: Brána firewall v místním počítači
Bránu v místním počítači, počítači, na kterém běží sady Visual Studio, není nastavit a povolit vzdálené ladění. Pro spravované nebo nativní vzdáleného ladění pomocí výchozí přenos, musí být otevřen port TCP 135 pro přenosy modelu DCOM. Sdílení souborů a tiskáren musí být otevřeno a devenv.exe musí být přidaný do seznamu výjimek. Otevírání některé porty protokolu IPSEC může být nutné také.  
  
 Další informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).