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
ms.openlocfilehash: 81d6aefcf98b43524e7ffa1e0965e6a5df9189fb
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49865723"
---
# <a name="secure-deployment"></a>Bezpečné nasazení
  Při vytváření řešení pro Office se automaticky aktualizuje vývojovém počítači povolíte kód v projektu pro spuštění. Ale když nasadíte řešení, je nutné zadat důkazy, na kterém chcete založit rozhodnutí o důvěryhodnosti řešení s certifikátem podepisování, nebo pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] výzvy klíč vztah důvěryhodnosti. Další informace najdete v tématu [zajištění důvěryhodnosti řešení pro systém Office](../vsto/granting-trust-to-office-solutions.md).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Pro přizpůsobení na úrovni dokumentu Pokud provádíte nasazení dokument do umístění v síti, musíte také přidat umístění dokumentu do seznamu důvěryhodných umístění v Centru zabezpečení aplikace Office. Další informace o tom, jak nastavit oprávnění k dokumentu v počítačích koncových uživatelů najdete v tématu [udělit důvěryhodnost dokumenty](../vsto/granting-trust-to-documents.md).  
  
## <a name="prevent-office-solutions-from-running-code"></a>Zabránit spuštění kódu řešení pro systém Office  
 Správcům umožňuje zabránit spuštěného na počítači všechna řešení pro Office v registru. Když řešení pro Office, který má rozšíření se spravovaným kódem se otevře, Visual Studio Tools for Office runtime kontroly, zda položka s názvem `Disabled` existuje pod jednou z následujících klíčů registru v počítači:  
  
- **HKEY_CURRENT_USER\Software\Microsoft\VSTO**  
  
- **Nenachází**  
  
  Chcete-li zabránit spuštění kódu řešení pro systém Office, vytvořte `Disabled` položku jeden nebo oba z těchto klíčů registru a zadejte jednu z následujících datových typů a hodnot pro `Disabled`:  
  
- REG_SZ nebo REG_EXPAND_SZ, který je nastaven na libovolný řetězec než "0" (nula).  
  
- REG_DWORD, která je nastavena na jakoukoli jinou hodnotu než 0 (nula).  
  
  Pokud chcete povolit řešení Office spuštění kódu, nastavte oba `Disabled` položky na hodnotu 0 (nula), nebo odstraňte položky registru.  
  
## <a name="see-also"></a>Viz také:  
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Příprava počítačů spustit nebo hostovat řešení pro systém Office](http://msdn.microsoft.com/be1b173f-7261-4d74-aa4e-94ccd43db8d8)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)  
  
  