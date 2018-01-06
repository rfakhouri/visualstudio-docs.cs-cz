---
title: "Postupy: přizpůsobení balíčku řešení služby SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.RAD.PackageDesignerAdvanced
- VS.SharePointTools.RAD.PackageDesigner.Manifest
- VS.SharePointTools.RAD.PackageDesignerProperties
- VS.SharePointTools.RAD.PackageDesigner.SwitchView
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, packages
ms.assetid: fd365f8c-8a80-4ce8-8e28-c0eb609f12f3
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5351165320dd0ff2d8c130c64adeff7be45de6fb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-a-sharepoint-solution-package"></a>Postupy: Přizpůsobení balíčku řešení služby SharePoint
  Návrháře balíčků můžete použít k vytvoření a úpravě balíčku (WSP). Můžete například přidat položky projektu služby SharePoint a funkcí, zadejte, jestli je webový server resetovat při nasazení řešení a nastavit typ serveru nasazení.  
  
## <a name="opening-the-package-designer"></a>Otevírání návrháře balíčků  
  
#### <a name="to-open-the-package-designer"></a>Chcete-li otevřít návrháře balíčků  
  
-   V **Průzkumníku řešení**, dvakrát klikněte na **balíček**, nebo zvolte **Návrhář zobrazení** v místní nabídce pro **balíček**.  
  
## <a name="viewing-the-packaged-manifest-file"></a>Zobrazení zabalené souboru manifestu  
 Návrháře balíčků můžete upravit a vytvořit zabalené soubor manifestu. Kód XML pro tento soubor pak můžete zobrazit v sadě Visual Studio.  
  
#### <a name="to-view-the-xml-source-file"></a>Chcete-li zobrazit zdrojový soubor XML  
  
1.  V **návrháře balíčků**, zvolte **Manifest**.  
  
#### <a name="to-view-the-packaged-manifest-file-by-using-solution-explorer"></a>Chcete-li zobrazit zabalené soubor manifestu pomocí Průzkumníku řešení  
  
1.  V **Průzkumníku řešení**, zvolte **zobrazit všechny soubory**.  
  
2.  Rozbalte balíček, Rozbalit Package.package a pak otevřete soubor Package.Template.xml.  
  
    > [!NOTE]  
    >  Otevřete soubor XML manifestu balíčku šablony, soubory se automaticky ověřují a můžete ignorovat upozornění, které se zobrazují v okně Seznam chyb.  
  
## <a name="changing-the-manifest-template"></a>Změna manifestu šablony  
 Můžete změnit kód XML pro zabalené souboru manifestu v editoru Visual Studio XML nebo v podokně manifestu šablony. Všechny změny kód XML jsou sloučeny do zabalené souboru manifestu balíčku.  
  
#### <a name="to-change-the-manifest-template-by-using-the-xml-editor"></a>Chcete-li změnit manifestu šablony pomocí editoru XML  
  
1.  V **návrháře balíčků**, vyberte **Manifest** rozbalte **upravit možnosti** uzel a potom zvolte **otevřete v editoru XML** odkaz.  
  
     Změny na XML jsou sloučeny do zabalené souboru manifestu.  
  
#### <a name="to-change-the-manifest-template-by-using-the-manifest-template-pane"></a>Chcete-li změnit manifestu šablony pomocí podokna manifestu šablony  
  
1.  V **návrháře balíčků**, vyberte **Manifest** rozbalte **upravit možnosti** uzel a poté změňte kód XML, který se zobrazí v podokně manifestu šablony.  
  
     Změny kódu XML zobrazí v **Preview z zabalené Manifest** podokně.  
  
## <a name="overwriting-the-packaged-manifest-file"></a>Přepsání zabalené souboru manifestu  
 Můžete zakázat návrháře balíčků a vytvoření souboru manifest.xml ručně. Při prvním provedení tohoto postupu, aktuální nastavení v Návrháři balíčku se ukládají do souboru XML balíčku šablony. Potom můžete upravit nebo přepsat kód XML.  
  
> [!NOTE]  
>  Pokud přidáte nebo odeberete položky projektu služby SharePoint a funkce v souboru XML návrháře balíčků je zakázáno, tyto položky projektu a funkce nejsou zabalené.  
  
#### <a name="to-overwrite-packaged-manifest-file-by-disabling-the-designer"></a>Chcete-li přepsat zabalené souboru manifestu zakázáním návrháře  
  
1.  V **návrháře balíčků**, vyberte **Manifest** kartě.  
  
2.  .  
  
3.  Rozbalte **upravit možnosti** uzlu, vyberte **přepsat vygenerovaný soubor XML a upravit manifest v editoru XML** propojit a potom zvolte **Ano** tlačítko.  
  
     Šablona se aktualizuje aktuální zabalené souboru manifestu.  
  
## <a name="enabling-the-package-designer"></a>Povolení návrháře balíčků  
 Úprava souboru manifest.xml návrháře balíčků můžete znovu povolit.  
  
#### <a name="to-re-enable-the-designer"></a>Chcete-li znovu povolit návrháře  
  
1.  V **návrháře balíčků**, vyberte **zahození manifestu úpravy a znovu povolte návrháře** propojit a potom zvolte **Ano** tlačítko.  
  
     Šablony je obnoví a zobrazí se původní text, a budou ztraceny všechny změny do souboru XML.  
  
## <a name="see-also"></a>Viz také  
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  