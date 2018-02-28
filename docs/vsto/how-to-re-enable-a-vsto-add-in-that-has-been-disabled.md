---
title: "Postupy: opětovné povolení doplňku VSTO, který byl zakázán | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.Warning.DisabledAddIn
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- disabled add-ins
- add-ins [Office development in Visual Studio], disabled
- add-ins [Office development in Visual Studio], enabling
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: c2f86906db578987ec81e35aa8c49abd62b5e88f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-re-enable-a-vsto-add-in-that-has-been-disabled"></a>Návody: Opětovné povolení zakázaného doplňku VSTO
  Aplikace Microsoft Office můžete zakázat doplňků VSTO které neočekávanému chování. Pokud při pokusu o jeho ladění nenačte vaší doplňku VSTO aplikace, aplikace může být pevný zakázaný nebo logicky zakázáno vaší doplňku VSTO.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
## <a name="hard-disabled-vsto-add-ins"></a>Doplňků VSTO pevný zakázáno  
 Zakázání pevného může dojít, když doplňku VSTO způsobí, že aplikace neočekávaně ukončena. Ho může také dojít k ve svém vývojovém počítači zastavení ladicího programu při <xref:Microsoft.Office.Tools.AddIn.Startup> spouští obslužné rutiny událostí v doplňku VSTO.  
  
#### <a name="to-re-enable-a-vsto-add-in"></a>Chcete-li znovu povolit doplňku VSTO  
  
1.  V aplikaci, klikněte **souboru** kartě.  
  
2.  Klikněte *ApplicationName* **možnosti** tlačítko.  
  
3.  V podokně kategorie, klikněte na **doplňky**.  
  
4.  V podokně podrobností ověřte, že doplňku VSTO zobrazuje v **aplikace zakázané doplňky** seznamu.  
  
     **Název** sloupce určuje název sestavení a **umístění** sloupce určuje úplnou cestu manifest aplikace.  
  
5.  V **spravovat** pole, klikněte na tlačítko **zakázané položky**a potom klikněte na **přejděte**.  
  
6.  Vyberte doplněk VSTO a klikněte na **povolit**.  
  
7.  Klikněte na tlačítko **Zavřít**.  
  
## <a name="soft-disabled-vsto-add-ins"></a>Doplňků VSTO konfigurace soft zakázaný  
 Logicky zakázání může dojít, když doplňku VSTO vytvoří chybu, který nevyvolá aplikace neočekávaně zavřete. Například aplikace může soft zakázat doplňku VSTO případě, že nastane neošetřenou výjimku při <xref:Microsoft.Office.Tools.AddIn.Startup> spouští obslužné rutiny události.  
  
> [!NOTE]  
>  Pokud znovu povolíte Add-in VSTO konfigurace soft zakázaný, pokusí se aplikace hned načíst doplňku VSTO. Pokud nebyl byl opraven problém, který původně důsledkem je aplikace logicky zakázat doplňku VSTO, aplikace bude soft zakázat doplňku VSTO znovu.  
  
#### <a name="to-re-enable-an-vsto-add-in"></a>Chcete-li znovu povolit doplňku VSTO  
  
1.  V aplikaci, klikněte **souboru** kartě.  
  
2.  Klikněte *ApplicationName* **možnosti** tlačítko.  
  
3.  V podokně kategorie, klikněte na **doplňky**.  
  
4.  V podokně podrobností ověřte, že doplňku VSTO zobrazuje v **neaktivní aplikace doplňky** seznamu.  
  
     **Název** sloupce určuje název sestavení a **umístění** sloupce určuje úplnou cestu manifest aplikace.  
  
5.  V **spravovat** pole, klikněte na tlačítko **COM Doplňky**a potom klikněte na **přejděte**.  
  
6.  V **COM Doplňky** dialogové okno, zaškrtněte políčko vedle zakázané VSTO doplněk.  
  
7.  Click **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření řešení pro systém Office](../vsto/building-office-solutions.md)   
 [Ladění projektů Office](../vsto/debugging-office-projects.md)   
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)  
  
  