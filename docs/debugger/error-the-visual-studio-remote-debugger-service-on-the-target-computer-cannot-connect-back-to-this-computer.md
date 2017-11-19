---
title: "Chyba: Visual Studio Debugger vzdálené služby v cílovém počítači nemůže připojit zpět k tomuto počítači | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.service_access_denied_oncallback
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 89ecf99d-66bf-4da0-a840-aa95b0be1702
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4f1707f7956557cb8ce764f66431dbf963dcfb79
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer"></a>Chyba: Služba vzdáleného ladicího programu sady Visual Studio na cílovém počítači se nemůže připojit zpět k tomuto počítači.
Tato chyba znamená, že služba Visual Studio Debugger vzdálené běží pod účtem uživatele, který nemůže ověřit při pokusu o připojení k počítači, který se ladění z.  
  
 Následující tabulka uvádí, co účty, můžete přístup k počítači:  
  
|||||  
|-|-|-|-|  
||Účet LocalSystem|Účet domény|Místní účty, které mají stejné uživatelské jméno a heslo na obou počítačích|  
|Oba počítače ve stejné doméně|Ano|Ano|Ano|  
|Oba počítače v doménách, které mají obousměrný vztah důvěryhodnosti|Ne|Ne|Ano|  
|Jeden nebo oba počítače v pracovní skupině|Ne|Ne|Ano|  
|Počítače v různých doménách|Ne|Ne|Ano|  
  
 Navíc:  
  
-   Účet, který spustíte Visual Studio Debugger vzdálené služby v rámci by měl být správce na vzdáleném počítači tak, aby ho můžete ladit jakýkoli proces.  
  
-   Účet má také oprávnění `Log on as a service` oprávnění ve vzdáleném počítači, který používá **místní zásady zabezpečení** nástroj pro správu.  
  
-   Pokud používáte pro přístup k účtu místního počítače, je nutné spustit službu Visual Studio Debugger vzdálené pod místním účtem.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Ujistěte se, že Visual Studio Debugger vzdálené služby je správně nastavena na vzdáleném počítači. Další informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).  
  
2.  Spusťte službu vzdáleného ladicího programu pod účtem, který má přístup k počítači hostitele ladicí program, jak je uvedeno v předchozí tabulce.  
  
### <a name="to-add-log-on-as-a-service-privilege"></a>Chcete-li přidat oprávnění "Přihlásit jako službu"  
  
1.  Na **spustit** nabídce zvolte **ovládací panely**.  
  
2.  V Ovládacích panelech vyberte **klasickém zobrazení**, v případě potřeby.  
  
3.  Klikněte dvakrát na **nástroje pro správu**.  
  
4.  V okně nástroje pro správu klikněte dvakrát na **místní zásady zabezpečení**.  
  
5.  V **místní nastavení zabezpečení** okno, rozbalte **místní zásady** složky.  
  
6.  Klikněte na tlačítko **přiřazení uživatelských práv**.  
  
7.  V **zásad** sloupce, klikněte dvakrát na **přihlásit jako službu** Chcete-li zobrazit aktuální přiřazení místních zásad skupiny v **přihlásit jako službu** dialogové okno.  
  
8.  Chcete-li přidat nové uživatele, klikněte na tlačítko **přidat uživatele nebo skupinu** tlačítko.  
  
9. Až dokončíte přidávání uživatelů, klikněte na tlačítko **OK**.  
  
### <a name="to-work-around-this-error"></a>Chcete-li vyřešit tuto chybu  
  
-   Spusťte sledování vzdáleného ladění jako aplikace místo služby.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)