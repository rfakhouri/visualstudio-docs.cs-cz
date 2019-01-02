---
title: 'Chyba: Sdílení souborů Windows bylo konfigurováno... | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.remote_credentials_prohibited
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
ms.openlocfilehash: 3bc3388bcf80d471c8dc6d45b0035f74d57abc93
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53942210"
---
# <a name="error-windows-file-sharing-has-been-configured"></a>Chyba: Sdílení souborů systému Windows bylo nakonfigurováno...
Sdílení souborů Windows nakonfigurovaný tak, aby se připojit ke vzdálenému počítači pomocí jiné uživatelské jméno. Toto je kompatibilní se vzdáleným laděním  
  
 Aktuální konfigurace sdílení souborů je nastavený pro připojení ke vzdálenému počítači pomocí jiné uživatelské jméno. Vzdálené ladění není možné v tomto scénáři.  
  
 Chcete-li opravit tuto chybu, přihlášení k počítači pomocí jiných názvu účtu, nebo změňte sdílení souborů použít název účtu, který ladíte, v části.  
  
 Pokud se chcete připojit ke vzdálenému počítači pomocí tohoto uživatelského jména, je nutné nejprve odpojit od vzdáleného počítače.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Přihlaste se na místním počítači, počítač, který ladíte, které pomocí jiných názvu účtu.  
  
     —nebo—  
  
     . Odpojit od vzdáleného počítače a překonfigurujte sdílení souborů pro připojení k počítači, pomocí názvu účtu:  
  
    1.  Na **Start** nabídky, přejděte k **Příslušenství**a potom klikněte na tlačítko **příkazový řádek**.  
  
    2.  Na příkazovém řádku Windows zadejte:  
  
         `net use /delete computer_name`  
  
    3.  Změňte nastavení sdílení souborů pomocí libovolné metody popsané v nápovědě k Windows.