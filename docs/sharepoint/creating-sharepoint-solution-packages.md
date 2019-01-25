---
title: Vytváření balíčků řešení služby SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
- packages [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 059bf8068ad3a14d01f0a8167900563eebdff215
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54867985"
---
# <a name="create-sharepoint-solution-packages"></a>Vytváření balíčků řešení služby SharePoint
  Pomocí návrháře balíčků, můžete vytvořit a přizpůsobit balíčky pro nasazení. Například můžete přidat položky Sharepointového projektu a funkce, obnovit server služby IIS, nastavit obory aktivace funkce a určit funkce závislostí. Návrhář také vygeneruje manifest, soubor XML, který popisuje každý balíček.  
  
## <a name="packaging-tools"></a>Nástroje pro balení
 Můžete použít **návrháři balíčku** přizpůsobit balíček a generování manifestu. Můžete zahrnout položky projektu služby SharePoint, nakonfigurovat, zda webový server by měl obnovit a nastavte typ serveru nasazení. Další informace najdete v tématu [jak: Přidání nebo odebrání funkcí a položek z balíku pomocí návrháře balíčků](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md).  
  
 Alternativně můžete použít **Průzkumník balení** upravit funkcí a položek v souboru balíčku (*.wsp*). Další informace najdete v tématu [jak: Přidání nebo odebrání funkcí a položek z balíku pomocí Průzkumníku balíčků](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer.md).  
  
 Visual Studio a nástroje MSBuild můžete použít k vytvoření balíčku (*.wsp*) soubory k nasazení řešení služby SharePoint. Tento proces vygeneruje soubory manifestu potřebné pro nasazení služby SharePoint. Další informace najdete v tématu [jak: Vytvoření balíčku řešení SharePoint pomocí úloh nástroje MSBuild](../sharepoint/how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks.md).  
  
## <a name="package-designer-options"></a>Možnosti návrháře balíčků
 V následující tabulce jsou uvedeny vlastnosti, které lze přizpůsobit v balíčcích Sharepointu s **návrháři balíčku**.  
  
|Vlastnost návrháře balíčku|Popis výchozí nastavení|  
|-------------------------------|------------------------------------|  
|Název|Povinný parametr. Výchozí název balíčku je nastavený na *ProjectName*.|  
|Reset WebServer|Volitelné. Vyberte, pokud chcete restartovat server po *.wsp* soubor je nainstalován na serveru SharePoint.|  
|Typ serveru nasazení|Povinný parametr. Ve výchozím oboru nastavena na ApplicationServer.<br /><br /> ApplicationServer: Popisuje, který je hostitelem služby server.<br /><br /> WebFrontEnd: Popisuje server, který je hostitelem webové stránky.|  
|Položky v řešení|Všechny položky Sharepointového projektu a funkce, které lze přidat do balíčku.|  
|Položky v balíčku|Volitelné. Všechny položky služby SharePoint a funkce, které chcete nasadit do balíčku.|  
  
## <a name="configure-the-packaging-process"></a>Konfigurace procesu vytváření balíčků
 Poté, co při vývoji řešení služby SharePoint v sadě Visual Studio, můžete přizpůsobit, jak jsou zabaleny projekty.  
  
 V následující tabulce jsou uvedeny dva cíle nástroje MSBuild, které vám umožní přizpůsobit způsob, jakým *.wsp* se vytvoří soubor.  
  
|Target|Popis|  
|------------|-----------------|  
|BeforeLayout|Cíl, který provádí úlohy bezprostředně před soubory se zkopírují do zprostředkující adresář. Soubory můžete upravit před vytvořením souboru balíčku (*.wsp*).|  
|AfterLayout|Cíl, který provádí úlohy ihned po soubory se zkopírují do zprostředkující adresář.|  
  
 Další informace najdete [jak: Přizpůsobení balíčku řešení SharePoint pomocí cílů nástroje MSBuild](../sharepoint/how-to-customize-a-sharepoint-solution-package-by-using-msbuild-targets.md).  
  
## <a name="packaging-architecture"></a>Architektura balíčku
 Když vytvoříte balíček Sharepointu, dojde k následujícím krokům (*.wsp*) v sadě Visual Studio.  
  
1.  Abyste měli jistotu, že je správná struktura fyzické a sémantická balíčku se ověří funkcí a balíčků.  
  
2.  Jsou uvedené funkce, položky projektu a balíček souborů v balíčku. Soubory manifestu pro balíčky a funkce jsou transformovány zahrnout všechny informace potřebné pro nasazení a aktivace. Tokeny jsou nahrazeny hodnotu plně kvalifikovaný.  
  
3.  Přizpůsobitelné cíl nástroje BeforeLayout MSBuild provádí. Můžete vytvořit tento krok proveďte vlastní úpravy na balíček před *.wsp* se vytvoří soubor.  
  
4.  Výčtové soubory se zkopírují do zprostředkující adresář.  
  
5.  Přizpůsobitelné cíl nástroje MSBuild AfterLayout provádí. Můžete vytvořit tento krok proveďte vlastní úpravy na balíček před *.wsp* se vytvoří soubor.  
  
6.  Soubory ve zprostředkujícím adresáři jsou přidány do *.wsp* souboru.  
  
## <a name="package-folder-structure"></a>Struktura složky balíčku
 Při balíčku projektu služby SharePoint *.wsp* je pro vás vytvoří soubor *SolutionFolder\bin\\\<BuildConfiguration >* složky. Například, pokud je vaše řešení v *C:\Visual Studio 2013\Projects\ListDefinition1* a konfigurace sestavení nastavená na verzi *.wsp* soubor se nachází v *2013\ C:\Visual Studio Projects\ListDefinition1\bin\Release*.  
  
## <a name="see-also"></a>Viz také:
 [Postupy: Přizpůsobení balíčku řešení služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)  
 [Postupy: Přidání nebo odebrání funkcí a položek z balíku pomocí návrháře balíčků](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)   
 [Postupy: Vytvoření balíčku řešení SharePoint pomocí úloh nástroje MSBuild](../sharepoint/how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks.md)   
 [Postupy: Vytvoření balíčku řešení SharePoint pomocí úloh nástroje MSBuild](../sharepoint/how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks.md)   
 [Postupy: Přizpůsobení balíčku řešení SharePoint pomocí cílů nástroje MSBuild](../sharepoint/how-to-customize-a-sharepoint-solution-package-by-using-msbuild-targets.md)  
