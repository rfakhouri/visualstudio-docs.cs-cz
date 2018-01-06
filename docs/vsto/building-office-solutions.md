---
title: "Vytváření řešení pro systém Office | Microsoft Docs"
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
- debugging [Office development in Visual Studio]
- debugging Office applications in Visual Studio
- solutions [Office development in Visual Studio], debugging
- Office applications [Office development in Visual Studio], debugging
- application development [Office development in Visual Studio], building
- Office applications [Office development in Visual Studio], building
- projects [Office development in Visual Studio], debugging
- Office solutions [Office development in Visual Studio], building
- solutions [Office development in Visual Studio], building
- Office projects [Office development in Visual Studio], debugging
- projects [Office development in Visual Studio], building
- builds [Office development in Visual Studio]
- Office projects [Office development in Visual Studio], building
- application development [Office development in Visual Studio], debugging
- Office solutions [Office development in Visual Studio], debugging
ms.assetid: c4b79ea8-df70-4a72-b76e-26e337d65727
caps.latest.revision: "39"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: cf3fde8e5a7e91719da11faca01453b405e30401
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="building-office-solutions"></a>Sestavování řešení pro systém Office
  Obecně platí, sestavování a ladění projektů Office je stejná jako sestavování a ladění jiné typy projektů v sadě Visual Studio, například Windows Forms. Témata v této části popisují rozdíly, které existují. Obecné informace o tom, jak vytvářet aplikace, najdete v tématu [kompilaci a sestavování v sadě Visual Studio](/visualstudio/ide/compiling-and-building-in-visual-studio).  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
## <a name="project-output-for-office-projects"></a>Výstup projektu pro projekty Office  
 Umístění výstupu pro projekty Office je *projectname*\bin\release nebo *projectname*\bin\debug. Nelze vytvořit do adresáře nasazení.  
  
### <a name="document-level-projects"></a>Projekty na úrovni dokumentu  
 Při sestavování projektu úrovni dokumentu ve výstupu projektu zahrnuje následující položky:  
  
-   Kopie projektu dokumentu.  
  
-   Sestavení projektu a všechny odkazované sestavení, které mají své **místní kopie** vlastnost nastavena na hodnotu **true**.  
  
-   Manifest aplikace, který má manifest příponu názvu souboru. Další informace najdete v tématu [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
-   Manifest nasazení, který má .vsto příponu názvu souboru. Další informace najdete v tématu [manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md).  
  
-   Soubor databáze (PDB) programu.  
  
> [!NOTE]  
>  Pokud vytvoříte řešení úrovni dokumentu do vzdáleného umístění namísto místního počítače, přidejte plně kvalifikovanou cestu do seznamu důvěryhodných umístění v Centru zabezpečení aplikace. Další informace najdete v tématu části s názvem udělení vztah důvěryhodnosti s dokumenty v [zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md).  
  
### <a name="application-level-projects"></a>Projekty na úrovni aplikace  
 Při sestavování projektu doplňku VSTO ve výstupu projektu zahrnuje následující položky:  
  
-   Sestavení projektu a všechny odkazované sestavení, které mají své **místní kopie** vlastnost nastavena na hodnotu **true**.  
  
-   Manifest aplikace, který má manifest příponu názvu souboru. Další informace najdete v tématu [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
-   Manifest nasazení, který má .vsto příponu názvu souboru. Další informace najdete v tématu [manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md).  
  
-   Soubor databáze (PDB) programu pro sestavení projektu.  
  
 Proces sestavení pro projekty doplňku VSTO také vytvoří sadu položky registru na vývojovém počítači, které jsou nutné k načtení doplňku VSTO. Další informace najdete v tématu [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).  
  
 Pokud vytvoříte projekt doplňku VSTO pro Outlook, který obsahuje oblasti formuláře, přidá procesu sestavení do registru následující doplňkové informace:  
  
-   Klíč pro každou třídu zpráv, který je přidružen jeden nebo více oblastí formulářů.  
  
-   Záznam pro každou oblast formuláře a přidružené hodnoty, který představuje název doplňku VSTO v Outlooku.  
  
 Aplikace Outlook potřebuje tyto informace načíst oblasti formuláře.  
  
## <a name="referenced-assemblies"></a>Odkazovaná sestavení  
 Sestavení (včetně projektů knihovny tříd), můžete odkazovat z projektu vytváření řešení pro systém Office. Každé odkazované sestavení má vlastnost s názvem **místní kopie**. **Zkopírujte místní** označuje, zda je sestavení zkopírovány do výstupního adresáře. Ve výchozím nastavení je nastavena na **true**. Každé odkazované sestavení, který má **místní kopie** nastavena na **true** zkopírován do výstupního adresáře.  
  
## <a name="security-during-the-build-process"></a>Zabezpečení během procesu sestavení  
 Visual Studio automaticky nakonfiguruje nastavení zabezpečení na vývojovém počítači můžete udělit vztah důvěryhodnosti k řešení během procesu vytváření. To umožňuje spustit, když ho ladění řešení.  
  
 Projekty Office používat certifikáty k ověření vydavatele. Visual Studio automaticky vytvoří dočasné certifikát k identifikaci řešení pro systém Office a nakonfiguruje vývojovém počítači dočasné certifikátu důvěřovat.  
  
 Další informace najdete v tématu [zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md).  
  
### <a name="network-projects"></a>Projekty sítě  
 Pokud umístění sestavení nebo dokument je ve sdílené síťové složce, místní aktualizace zásad zabezpečení (uživatel úroveň) není dostatečná k povolení spuštění řešení. Správce musí udělit úplný vztah důvěryhodnosti na úrovni počítače pro sestavení a dokumenty, které jsou ve sdílené síťové složce, než se spustí řešení. Další informace o tom, jak nastavit zásady zabezpečení najdete v tématu [zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md).  
  
 Pro projekty na úrovni dokumentu musíte taky přidat plně kvalifikovaný umístění dokumentu do seznamu důvěryhodných složky Office. Další informace najdete v tématu [udělení vztah důvěryhodnosti s dokumenty](../vsto/granting-trust-to-documents.md).  
  
## <a name="changing-the-platform-target"></a>Změna cílové platformy  
 Ve výchozím nastavení, je cílová platforma pro projekty Office **libovolný procesor**. Obvykle byste neměli měnit toto nastavení. Řešení Office, které jsou vytvořeny pomocí **libovolný procesor** Cílová platforma nastavení spuštění v 32bitové a 64bitové verze Microsoft [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] nebo [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)].  
  
 Měli byste nastavit Cílová platforma hodnotu x64 pouze v případě, že vytváříte řešení, které se spustí pouze v 64bitových verzích Microsoft [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] nebo [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)], a řešení pro volání rozhraní API nativní 64bitové verze. Další informace o změně nastavení cílové platformy najdete v tématu [postupy: Konfigurace projektů pro cílové platformy](../ide/how-to-configure-projects-to-target-platforms.md).  
  
 Pokud nastavíte Cílová platforma x64, řešení nespustí v 32bitové verze systému Windows nebo Office. X64 Cílová platforma vyžaduje řešení, aby byla spuštěna v procesu 64-bit.  
  
## <a name="using-the-clean-command"></a>Pomocí příkazu vyčištění  
 Pokud chcete odebrat soubory vytvořené projektu ze vývojovém počítači, můžete použít **Vyčistit** příkaz na **sestavení** nabídky v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. **Vyčistit** příkaz odstraní všechny soubory v umístění výstupu sestavení. Pro projekty na úrovni aplikace **Vyčistit** příkaz také odebere položky registru, které jsou vytvořené pomocí procesu sestavení.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Ladění projektů Office](../vsto/debugging-office-projects.md)|Uvede problémy při ladění projektů Office.|  
|[Návod: Vytvoření prvního přizpůsobení na úrovni dokumentu pro Excel](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)|Ukazuje, jak vytvořit základní přizpůsobení na úrovni dokumentu pro Excel.|  
|[Návody: Opětovné povolení zakázaného doplňku VSTO](../vsto/how-to-re-enable-a-vsto-add-in-that-has-been-disabled.md)|Popisuje, jak znovu zapnout VSTO doplněk, který byl pevného nebo soft zakázán.|  
|[Navrhování a tvorba řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)|Obsahuje odkazy na informace o vytváření řešení pro systém Office a o roli sestavení v řešení.|  
  
  