---
title: 'Chyba: Služba Visual Studio Remote Debugger na cílovém počítači se nemůže připojit zpět k tomuto počítači | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.service_access_denied_oncallback
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 89ecf99d-66bf-4da0-a840-aa95b0be1702
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8f598d765e45b1f97d6a3e95d1ad57c325ea38fe
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697350"
---
# <a name="error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer"></a>Chyba: Služba Visual Studio Remote Debugger na cílovém počítači se nemůže připojit zpět k tomuto počítači
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato chyba znamená, že se službou Visual Studio Remote Debugger uživatelského účtu, který nelze ověřit při pokusu o připojení k počítači, který ladíte z.  
  
 V následující tabulce jsou uvedeny účty, které je přístupné počítači:  
  
|||||  
|-|-|-|-|  
||Účet LocalSystem|Účet domény|Místní účty, které mají stejné uživatelské jméno a heslo na obou počítačích|  
|Oba počítače ve stejné doméně.|Ano|Ano|Ano|  
|Oba počítače v doménách s obousměrným vztahem důvěryhodnosti|Ne|Ne|Ano|  
|Jeden nebo oba počítače v pracovní skupině|Ne|Ne|Ano|  
|Počítače v různých doménách|Ne|Ne|Ano|  
  
 Navíc:  
  
- Účet, který spustíte v rámci služby Visual Studio Remote Debugger by měl být správce na vzdáleném počítači tak, aby ho můžete ladit nějaký proces.  
  
- Účet také musí být udělena `Log on as a service` oprávnění ve vzdáleném počítači, který se používá **místní zásady zabezpečení** nástroje pro správu.  
  
- Pokud používáte místní účet přístupu k počítači, je nutné spustit pod účtem místní služby Visual Studio Remote Debugger.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1. Ujistěte se, že služba Visual Studio Remote Debugger je správně nastavený na vzdáleném počítači. Další informace najdete v tématu [nastavit Up the Remote Tools na zařízení](https://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c).  
  
2. Spusťte službu vzdálený ladicí program pomocí účtu, který má přístup k počítači hostitele ladicího programu, jak je znázorněno v předchozí tabulce.  
  
### <a name="to-add-log-on-as-a-service-privilege"></a>Chcete-li přidat oprávnění "Přihlásit jako službu"  
  
1. Na **Start** nabídce zvolte **ovládací panely**.  
  
2. V Ovládacích panelech zvolte **klasické zobrazení**, v případě potřeby.  
  
3. Dvakrát klikněte na panel **nástroje pro správu**.  
  
4. V okně nástroje pro správu, klikněte dvakrát na **místní zásady zabezpečení**.  
  
5. V **místní nastavení zabezpečení** okna, rozbalte **místní zásady** složky.  
  
6. Klikněte na tlačítko **přiřazení uživatelských práv**.  
  
7. V **zásady** sloupce, klikněte dvakrát na **přihlásit jako službu** zobrazíte aktuální místní zásady skupiny přiřazení v **přihlásit jako službu** dialogové okno.  
  
8. Pokud chcete přidat nové uživatele, klikněte na tlačítko **přidat uživatele nebo skupinu** tlačítko.  
  
9. Po dokončení přidávání uživatelů, klikněte na tlačítko **OK**.  
  
### <a name="to-work-around-this-error"></a>Chcete-li vyřešit tuto chybu  
  
- Spuštění sledování vzdáleného ladění jako aplikace místo jako služba.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)
