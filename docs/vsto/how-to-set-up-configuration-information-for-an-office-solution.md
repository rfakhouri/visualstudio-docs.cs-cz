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
ms.assetid: f123838f-957a-4cf5-acc0-0cc0f4c2aea2
caps.latest.revision: "33"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: d7b8c8c9ca6dd964a58aa65b901d9219732179f3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
  