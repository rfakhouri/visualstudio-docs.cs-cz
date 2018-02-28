---
title: "Chyba: Sdílení souborů systému Windows byl nakonfigurován... | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.remote_credentials_prohibited
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7bbd8d00a6939030068bbe6dd565fb57393d18be
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="error-windows-file-sharing-has-been-configured"></a>Chyba: Sdílení souborů systému Windows bylo konfigurováno...
Sdílení souborů systému Windows je nakonfigurovaný tak, aby se připojit ke vzdálenému počítači pomocí jiné uživatelské jméno. Toto je kompatibilní s vzdálené ladění  
  
 Aktuální konfigurace sdílení souborů je nastavený pro připojení ke vzdálenému počítači pomocí jiné uživatelské jméno. Vzdálené ladění není možné v tomto scénáři.  
  
 Chcete-li opravit tuto chybu, přihlášení k počítači pomocí jiných název účtu nebo změňte sdílení souborů pro použití názvu účtu, pod kterou ladíte.  
  
 Pokud se chcete připojit ke vzdálenému počítači pomocí tohoto uživatelského jména, je nutné nejprve odpojit ze vzdáleného počítače.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Přihlaste se do místního počítače, počítač, kterou ladíte, pomocí jiných název účtu.  
  
     —nebo—  
  
     . Odpojení ze vzdáleného počítače a překonfigurujte sdílení souborů pro připojení k jiným počítačem pomocí název účtu:  
  
    1.  Na **spustit** nabídky, přejděte na příkaz **Příslušenství**a potom klikněte na **příkazového řádku**.  
  
    2.  Na příkazovém řádku Windows zadejte:  
  
         `net use /delete computer_name`  
  
    3.  Změňte nastavení sdílení souborů pomocí metod najdete v nápovědě k systému Windows.