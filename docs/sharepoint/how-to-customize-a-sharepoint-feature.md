---
title: "Postupy: přizpůsobení funkce služby SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.RAD.FeatureDesigner.SwitchView
- VS.SharePointTools.RAD.featureDesigner.Manifest
- VS.SharePointTools.RAD.FeatureDesignerProperties
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, features
ms.assetid: e624c546-564b-4c73-9f1b-dc3675e76a55
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 0ed5ca134205568a185541b64e3f22cc4f76ed36
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-a-sharepoint-feature"></a>Postupy: Přizpůsobení funkce služby SharePoint
  Můžete vytvořit a přizpůsobit funkcí služby SharePoint pomocí návrháře funkce v sadě Visual Studio. Můžete například nastavit obor funkcí a přidat další funkce, jako závislosti. Ve výchozím nastavení je otevřené návrháře funkce při přidání nové funkce v Průzkumníku řešení nebo balíček Průzkumníka služby SharePoint.  
  
## <a name="opening-the-feature-designer"></a>Otevírání návrháře funkce  
 Můžete přidat nebo odebrat položky projektu služby SharePoint pomocí návrháře funkce funkce.  
  
#### <a name="to-open-the-feature-designer"></a>Chcete-li spustit funkci návrháře  
  
1.  V **Průzkumníku řešení**, rozbalte položku **funkce**.  
  
2.  Dvakrát klikněte *Feature1* položku nebo otevřít místní nabídku pro *Feature1* položky a potom zvolte **Návrhář zobrazení**.  
  
## <a name="viewing-the-packaged-manifest-file"></a>Zobrazení zabalené souboru manifestu  
 Návrhář funkce můžete upravit a vytvořit zabalené soubor manifestu pro funkci (souboru funkce.XML). Kód XML pro tento soubor pak můžete zobrazit v sadě Visual Studio.  
  
#### <a name="to-view-the-packaged-manifest-file"></a>Chcete-li zobrazit zabalené souboru manifestu  
  
1.  V **funkce Návrhář**, vyberte **Manifest** kartě.  
  
#### <a name="to-view-the-packaged-manifest-file-by-using-solution-explorer"></a>Chcete-li zobrazit zabalené soubor manifestu pomocí Průzkumníku řešení  
  
1.  V **Průzkumníku řešení**, vyberte **zobrazit všechny soubory** ikonu.  
  
2.  Rozbalte funkce, rozbalte FeatureName, rozbalte položku FeatureName.feature a pak otevřete *FeatureName*. Souboru template.XML.  
  
    > [!NOTE]  
    >  Otevřete soubor manifestu XML funkce šablony, soubory se automaticky ověřují a můžete ignorovat upozornění, která se zobrazí v okně Seznam chyb.  
  
## <a name="changing-the-manifest-template"></a>Změna manifestu šablony  
 Můžete změnit kód XML pro soubor manifestu funkce v editoru Visual Studio XML nebo v podokně manifestu šablony. Všechny změny kód XML je pro funkci sloučí zabalené souboru manifestu. Můžete například změnit manifestu šablony, chcete-li přizpůsobit vlastnosti funkce.  
  
#### <a name="to-change-the-manifest-template-by-using-the-xml-editor"></a>Chcete-li změnit manifestu šablony pomocí editoru XML  
  
1.  V **funkce Návrhář**, vyberte **Manifest** rozbalte **upravit možnosti** uzel a potom vyberte **otevřete v editoru XML** odkaz.  
  
     Změny na XML jsou sloučeny do zabalené souboru manifestu.  
  
#### <a name="to-change-the-manifest-template-by-using-the-manifest-template-pane"></a>Chcete-li změnit manifestu šablony pomocí podokna manifestu šablony  
  
1.  V **funkce Návrhář**, vyberte **Manifest** rozbalte **upravit možnosti** uzel a poté změňte kód XML, který se zobrazí v podokně manifestu šablony.  
  
     Změny kódu XML zobrazí v **Preview z zabalené Manifest** podokně.  
  
## <a name="overwriting-the-packaged-manifest-file"></a>Přepsání zabalené souboru manifestu  
 Můžete zakázat návrháře funkce a vytvoření souboru souboru funkce.XML ručně. Při prvním provedení tohoto postupu, aktuální nastavení v Návrháři funkce se ukládají do souboru XML šablony funkce. Potom můžete upravit nebo přepsat kód XML.  
  
> [!NOTE]  
>  Je-li přidat nebo odebrat SharePoint – položky projektu v souboru XML, zatímco návrháře funkce je zakázaná, nejsou zabalené tyto položky projektu.  
  
#### <a name="to-overwrite-packaged-manifest-file-by-disabling-the-designer"></a>Chcete-li přepsat zabalené souboru manifestu zakázáním návrháře  
  
1.  V **funkce Návrhář**, vyberte **Manifest** kartě.  
  
2.  Rozbalte **upravit možnosti** uzlu, vyberte **přepsat vygenerovaný soubor XML a upravit manifest v editoru XML** propojit a potom zvolte **Ano** tlačítko.  
  
     Šablona se aktualizuje aktuální zabalené souboru manifestu.  
  
## <a name="enabling-the-feature-designer"></a>Povolení funkce návrháře  
 Můžete znovu povolit funkci návrháře k přizpůsobení souboru funkce.XML souboru.  
  
#### <a name="to-re-enable-the-designer"></a>Chcete-li znovu povolit návrháře  
  
1.  V **funkce Návrhář**, vyberte **zahození manifestu úpravy a znovu povolte návrháře** propojit a potom zvolte **Ano** tlačítko.  
  
2.  Šablony je obnoví a zobrazí se původní text, a budou ztraceny všechny změny do souboru XML.  
  
## <a name="see-also"></a>Viz také  
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  