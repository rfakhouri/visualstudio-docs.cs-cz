---
title: 'Chyba: Sdílení souborů Windows bylo konfigurováno... | Dokumentace Microsoftu'
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
- vs.debug.error.remote_credentials_prohibited
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: c45a1b74-61ec-4c64-9e2c-13051a4f50a5
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9fc4d3fb02b1c7c9d5003f82fbe42be73c93d6eb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666365"
---
# <a name="error-windows-file-sharing-has-been-configured"></a>Chyba: Sdílení souborů systému Windows bylo konfigurováno...
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: sdílení souboru Windows bylo konfigurováno... ](https://docs.microsoft.com/visualstudio/debugger/error-windows-file-sharing-has-been-configured-dot-dot-dot).  
  
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



