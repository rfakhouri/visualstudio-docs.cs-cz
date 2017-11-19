---
title: "Chyba: Brány Firewall v místním počítači | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.firewall.localmachine
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: ab60dda9-7934-4891-aa2f-001380d2ed83
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0eb7158fe2274fbe8707a147fe63a0937689d23
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-firewall-on-local-machine"></a>Chyba: Brána firewall v místním počítači
Bránu v místním počítači, počítači, na kterém běží sady Visual Studio, není nastavit a povolit vzdálené ladění. Pro spravované nebo nativní vzdáleného ladění pomocí výchozí přenos, musí být otevřen port TCP 135 pro přenosy modelu DCOM. Sdílení souborů a tiskáren musí být otevřeno a devenv.exe musí být přidaný do seznamu výjimek. Otevírání některé porty protokolu IPSEC může být nutné také.  
  
 Další informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).