---
title: 'Chyba: Služba Visual Studio Remote Debugger na cílovém počítači se nemůže znovu připojit k tomuto počítači.'
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.service_access_denied_oncallback
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c07557fa64f86349a3baf8956d99b937ceab9f5a
ms.sourcegitcommit: 9753c7544cec852ca5efd0834e0956d9e53a5734
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043441"
---
# <a name="error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer"></a>Chyba: Služba Visual Studio Remote Debugger na cílovém počítači se nemůže znovu připojit k tomuto počítači.
Tato chyba znamená, že služba vzdáleného ladění běží pod účtem uživatele, které nelze ověřit při pokusu o připojení k počítači, který ladíte z. K této chybě může dojít při vzdáleném ladění pomocí starší verze modulu pro ladění a vzdálený ladicí program je spuštěn jako služba.

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

1. Ujistěte se, že služba Visual Studio Remote Debugger je správně nastavený na vzdáleném počítači. Další informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).

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
- [Chyby při vzdáleném ladění a jejich řešení](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Vzdálené ladění](../debugger/remote-debugging.md)