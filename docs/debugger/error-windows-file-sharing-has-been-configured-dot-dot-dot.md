---
title: 'Chyba: Sdílení souborů Windows bylo konfigurováno... | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.remote_credentials_prohibited
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: c45a1b74-61ec-4c64-9e2c-13051a4f50a5
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 89224dc5394f248ea82d428731ef387cb705ff27
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850047"
---
# <a name="error-windows-file-sharing-has-been-configured"></a>Chyba: Sdílení souborů systému Windows bylo nakonfigurováno...
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Sdílení souborů Windows nakonfigurovaný tak, aby se připojit ke vzdálenému počítači pomocí jiné uživatelské jméno. Toto je kompatibilní se vzdáleným laděním  
  
 Aktuální konfigurace sdílení souborů je nastavený pro připojení ke vzdálenému počítači pomocí jiné uživatelské jméno. Vzdálené ladění není možné v tomto scénáři.  
  
 Chcete-li opravit tuto chybu, přihlášení k počítači pomocí jiných názvu účtu, nebo změňte sdílení souborů použít název účtu, který ladíte, v části.  
  
 Pokud se chcete připojit ke vzdálenému počítači pomocí tohoto uživatelského jména, je nutné nejprve odpojit od vzdáleného počítače.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1. Přihlaste se na místním počítači, počítač, který ladíte, které pomocí jiných názvu účtu.  
  
     —nebo—  
  
     . Odpojit od vzdáleného počítače a překonfigurujte sdílení souborů pro připojení k počítači, pomocí názvu účtu:  
  
    1. Na **Start** nabídky, přejděte k **Příslušenství**a potom klikněte na tlačítko **příkazový řádek**.  
  
    2. Na příkazovém řádku Windows zadejte:  
  
         `net use /delete computer_name`  
  
    3. Změňte nastavení sdílení souborů pomocí libovolné metody popsané v nápovědě k Windows.
