---
title: 'Chyba: Brány Firewall v místním počítači | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.firewall.localmachine
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 98badb458be79e17684c5ce134813d25b6605352
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="error-firewall-on-local-machine"></a>Chyba: Brána firewall v místním počítači
Bránu v místním počítači, počítači, na kterém běží sady Visual Studio, není nastavit a povolit vzdálené ladění. Pro spravované nebo nativní vzdáleného ladění pomocí výchozí přenos, musí být otevřen port TCP 135 pro přenosy modelu DCOM. Sdílení souborů a tiskáren musí být otevřeno a devenv.exe musí být přidaný do seznamu výjimek. Otevírání některé porty protokolu IPSEC může být nutné také.  
  
 Další informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).