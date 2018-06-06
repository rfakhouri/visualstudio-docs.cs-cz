---
title: Bezpečné nasazení
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- deploying applications [Office development in Visual Studio], security
- Office development in Visual Studio, security
- Office applications [Office development in Visual Studio], security
- ClickOnce deployment [Office development in Visual Studio], security
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 47cecda571a6826c2d7e845945c05d0264971134
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693328"
---
# <a name="secure-deployment"></a>Bezpečné nasazení
  Při vytváření řešení Office vývojovém počítači se aktualizuje automaticky povolit kód ve vašem projektu a spustit. Ale když nasadíte řešení, je nutné zadat důkaz, na které se mají základní rozhodnutí o vztahu důvěryhodnosti podepisování řešení s certifikátem, nebo pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] klíč výzvy důvěryhodnosti. Další informace najdete v tématu [udělit vztah důvěryhodnosti řešení pro systém Office](../vsto/granting-trust-to-office-solutions.md).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Pro úpravy na úrovni dokumentů Pokud nasazujete dokument do umístění v síti, musíte taky přidat dokumentu umístění do seznamu důvěryhodných umístění v Centru zabezpečení aplikace Office. Další informace o tom, jak nastavit oprávnění dokumentu pro koncového uživatele počítačů najdete v tématu [udělit vztah důvěryhodnosti k dokumentům](../vsto/granting-trust-to-documents.md).  
  
## <a name="prevent-office-solutions-from-running-code"></a>Zabránit spuštění kódu řešení pro systém Office  
 Správci můžou pomocí registru všechna řešení pro systém Office bránit ve spouštění v počítači. Při řešení Office, který se má spravovat rozšíření kódu je otevřené, Visual Studio Tools for Office runtime kontroly zda položka s názvem `Disabled` existuje pod jednou z následujících klíčů registru v počítači:  
  
-   **HKEY_CURRENT_USER\Software\Microsoft\VSTO**  
  
-   **HKEY_LOCAL_MACHINE\Software\Microsoft\VSTO**  
  
 Chcete-li zabránit spuštění kódu řešení pro systém Office, vytvořte `Disabled` položky v rámci jedna nebo obě tyto klíče registru a určete jednu z následujících datových typů a hodnot pro `Disabled`:  
  
-   REG_SZ nebo REG_EXPAND_SZ, který je nastavený na libovolný řetězec než "0" (nula).  
  
-   REG_DWORD, který je nastavený na jakoukoli jinou hodnotu než 0 (nula).  
  
 Pokud chcete povolit spuštění kódu řešení systému Office, nastavte oba `Disabled` položky na hodnotu 0 (nula), nebo odstranění položek registru.  
  
## <a name="see-also"></a>Viz také:  
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Příprava počítačů ke spuštění nebo hostitele řešení pro systém Office](http://msdn.microsoft.com/en-us/be1b173f-7261-4d74-aa4e-94ccd43db8d8)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)  
  
  