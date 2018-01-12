---
title: "Postupy: nastavení informací o konfiguraci pro řešení Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], configuration files
- configuration files [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6f604fa40a9816d5e46593bc50fcb91f82d13325
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-set-up-configuration-information-for-an-office-solution"></a>Postupy: Nastavení informací o konfiguraci u řešení pro systém Office
  Konfigurační soubory můžete použít ke konfiguraci nastavení, které jsou specifické pro vaše řešení pro systém Office. Můžete zadat nastavení jako zásady vazby sestavení, ladění, vzdálenou komunikaci objektů a nastavení trasování.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-configuration-file-to-your-office-project"></a>Chcete-li přidat konfigurační soubor do projektu Office  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
2.  V **kategorie** podokně klikněte na tlačítko **Obecné**.  
  
3.  V **šablony** podokně, vyberte **konfigurační soubor aplikace**.  
  
4.  V **název** zadejte stejný název jako sestavení plus .config rozšíření. Například konfiguračního souboru pro sestavení projektu aplikace Excel nazvané ExcelWorkbook1.dll by se jmenovala ExcelWorkbook1.dll.config.  
  
5.  Klikněte na tlačítko **přidat**.  
  
6.  Vytvoření konfiguračního souboru podle schéma konfiguračního souboru aplikace. Další informace najdete v tématu [schéma konfiguračního souboru pro rozhraní .NET Framework](/dotnet/framework/configure-apps/file-schema/index).  
  
 Neexistují žádné zvláštní požadavky pro použití konfigurační soubory s projekty Office.  
  
## <a name="see-also"></a>Viz také  
 [Schéma konfiguračního souboru pro rozhraní .NET Framework](/dotnet/framework/configure-apps/file-schema/index)   
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)  
  
  