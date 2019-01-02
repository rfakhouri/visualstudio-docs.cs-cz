---
title: 'Postupy: Přizpůsobení balíčku řešení služby SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.RAD.PackageDesignerAdvanced
- VS.SharePointTools.RAD.PackageDesigner.Manifest
- VS.SharePointTools.RAD.PackageDesignerProperties
- VS.SharePointTools.RAD.PackageDesigner.SwitchView
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 85140f8d85c90d2b58df10a63f50c117e10eb8bd
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53835393"
---
# <a name="how-to-customize-a-sharepoint-solution-package"></a>Postupy: Přizpůsobení balíčku řešení služby SharePoint
  Návrháři balíčku můžete použít k vytvoření a přizpůsobení balíčku (*.wsp*). Například můžete přidat položky Sharepointového projektu a funkce, určete, jestli je webový server obnovit, když se řešení nasadí a nastavit typ serveru nasazení.  
  
## <a name="open-the-package-designer"></a>Otevřít návrháře balíčků  
  
#### <a name="to-open-the-package-designer"></a>Chcete-li otevřít návrháře balíčků
  
-   V **Průzkumníka řešení**, dvakrát klikněte na panel **balíčku**, nebo zvolte **Návrhář zobrazení** v místní nabídce pro **balíčku**.  
  
## <a name="view-the-packaged-manifestffile"></a>Zobrazení zabalené manifestfFile  
 Návrháři balíčku můžete použít k úpravě a generování souboru manifestu balíčku. Kód XML pro tento soubor pak můžete zobrazit v sadě Visual Studio.  
  
#### <a name="to-view-the-xml-source-file"></a>Chcete-li zobrazit zdrojový soubor XML  
  
1.  V **návrháři balíčku**, zvolte **Manifest**.  
  
#### <a name="to-view-the-packaged-manifest-file-by-using-solution-explorer"></a>Chcete-li zobrazit souboru manifestu balíčku pomocí Průzkumníka řešení  
  
1.  V **Průzkumníka řešení**, zvolte **zobrazit všechny soubory**.  
  
2.  Rozbalte balíček, Rozbalit Package.package a pak otevřete *Package.Template.xml* souboru.  
  
    > [!NOTE]  
    >  Když otevřete soubor manifestu XML pro balíček šablony, soubory se automaticky ověří a můžete ignorovat upozornění, které se zobrazí v okně Seznam chyb.  
  
## <a name="change-the-manifest-template"></a>Změny v šabloně manifestu  
 Můžete změnit kód XML pro zabalené soubor manifestu v editoru XML sady Visual Studio nebo v podokně šablony manifestu. Jakékoli změny kódu XML jsou sloučeny do souboru manifestu balíčku pro balíček.  
  
#### <a name="to-change-the-manifest-template-by-using-the-xml-editor"></a>Chcete-li změnit šablonu manifestu pomocí editoru XML  
  
1.  V **návrháři balíčku**, zvolte **Manifest** kartu, rozbalte **upravit možnosti** uzel a klikněte na tlačítko **otevřené v editoru XML** odkaz.  
  
     Změny do souboru XML jsou sloučeny do souboru manifestu balíčku.  
  
#### <a name="to-change-the-manifest-template-by-using-the-manifest-template-pane"></a>Chcete-li změnit šablonu manifestu pomocí podokna manifestu šablony  
  
1.  V **návrháři balíčku**, zvolte **Manifest** kartu, rozbalte **upravit možnosti** uzel a poté změňte kód XML, který se zobrazí v podokně šablony manifestu.  
  
     Změny v souboru XML se zobrazí v **ve verzi Preview ze zabalené Manifest** podokně.  
  
## <a name="overwrite-the-packaged-manifest-file"></a>Přepsání souboru manifestu balíčku  
 Můžete zakázat návrháře balíčků a vytvoření *manifest.xml* soubor ručně. Při prvním provedení tohoto postupu, aktuální nastavení v Návrháři balíčku se uloží do souboru XML balíčku šablony. Potom můžete upravit nebo přepsat kód XML.  
  
> [!NOTE]  
>  Je-li přidat nebo odebrat položky Sharepointového projektu a funkce v souboru XML, návrháři balíčku je zakázáno, tyto položky projektu a funkce nejsou zabaleny.  
  
#### <a name="to-overwrite-packaged-manifest-file-by-disabling-the-designer"></a>K přepsání souboru manifestu balíčku zakázáním návrháře  
  
1.  V **návrháři balíčku**, zvolte **Manifest** kartu.  
  
2.  Rozbalte **upravit možnosti** uzlu, vyberte **přepsat vygenerovaný kód XML a upravit manifest v editoru XML** propojit a klikněte na tlačítko **Ano** tlačítko.  
  
     Šablona se aktualizuje aktuální soubor manifestu balíčku.  
  
## <a name="enable-the-package-designer"></a>Povolit návrháře balíčků  
 Můžete znovu povolit návrháři balíček si můžete přizpůsobit *manifest.xml* souboru.  
  
#### <a name="to-re-enable-the-designer"></a>Chcete-li znovu povolí návrháře  
  
1.  V **návrháři balíčku**, zvolte **zahodit úpravy manifestu a znovu povolí návrháře** propojit a klikněte na tlačítko **Ano** tlačítko.  
  
     Šablona se aktualizuje s původním textem a budou ztraceny všechny změny do souboru XML.  
  
## <a name="see-also"></a>Viz také:
 [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
