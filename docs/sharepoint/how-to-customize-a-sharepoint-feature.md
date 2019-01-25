---
title: 'Postupy: Přizpůsobení funkce služby SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.RAD.FeatureDesigner.SwitchView
- VS.SharePointTools.RAD.featureDesigner.Manifest
- VS.SharePointTools.RAD.FeatureDesignerProperties
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, features
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 867eb1fd64a7318d460a387ededd39e4f188d445
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54868102"
---
# <a name="how-to-customize-a-sharepoint-feature"></a>Postupy: Přizpůsobení funkce služby SharePoint
  Můžete vytvořit a přizpůsobit funkce služby SharePoint pomocí návrháře funkcí v sadě Visual Studio. Můžete například nastavit obor funkce a přidat další funkce jako závislosti. Ve výchozím nastavení je otevřený Návrhář funkce při přidání nové funkce v Průzkumníku řešení nebo Průzkumníku balíčků služby SharePoint.  
  
## <a name="opening-the-feature-designer"></a>Otevření Návrháře funkcí  
 Můžete přidat nebo odebrat položky Sharepointového projektu do funkce pomocí návrháře funkcí.  
  
#### <a name="to-open-the-feature-designer"></a>Chcete-li otevřít návrháře funkcí
  
1.  V **Průzkumníka řešení**, rozbalte **funkce**.  
  
2.  Dvakrát klikněte *Feature1* položku nebo otevřete místní nabídku pro *Feature1* položku a pak zvolte **Návrhář zobrazení**.  
  
## <a name="view-the-packaged-manifest-file"></a>Zobrazení souboru manifestu balíčku  
 Můžete použít Návrháře funkcí upravit a generovat souboru manifestu balíčku pro funkci (*feature.xml*). Kód XML pro tento soubor pak můžete zobrazit v sadě Visual Studio.  
  
#### <a name="to-view-the-packaged-manifest-file"></a>Chcete-li zobrazit souboru manifestu balíčku  
  
1.  V **návrháře funkcí**, zvolte **Manifest** kartu.  
  
#### <a name="to-view-the-packaged-manifest-file-by-using-solution-explorer"></a>Chcete-li zobrazit souboru manifestu balíčku pomocí Průzkumníka řešení  
  
1.  V **Průzkumníka řešení**, zvolte **zobrazit všechny soubory** ikonu.  
  
2.  Rozbalte funkce, rozbalte FeatureName, rozbalte FeatureName.feature a pak otevřete  *\<FeatureName >. Template.xml* souboru.  
  
    > [!NOTE]  
    >  Když otevřete soubor manifestu XML funkce šablony, soubory se automaticky ověří a upozornění, která se zobrazí v okně Seznam chyb můžete ignorovat.  
  
## <a name="change-the-manifest-template"></a>Změny v šabloně manifestu  
 Můžete změnit kód XML pro soubor manifestu funkce v editoru XML sady Visual Studio nebo v podokně šablony manifestu. Jakékoli změny kódu XML se sloučí do souboru manifestu balíčku pro funkci. Můžete například změnit v šabloně manifestu pro přizpůsobení vlastnost funkce.  
  
#### <a name="to-change-the-manifest-template-by-using-the-xml-editor"></a>Chcete-li změnit šablonu manifestu pomocí editoru XML  
  
1.  V **návrháře funkcí**, zvolte **Manifest** kartu, rozbalte **upravit možnosti** uzel a klikněte na tlačítko **otevřené v editoru XML** odkaz.  
  
     Změny do souboru XML jsou sloučeny do souboru manifestu balíčku.  
  
#### <a name="to-change-the-manifest-template-by-using-the-manifest-template-pane"></a>Chcete-li změnit šablonu manifestu pomocí podokna manifestu šablony  
  
1.  V **návrháře funkcí**, zvolte **Manifest** kartu, rozbalte **upravit možnosti** uzel a poté změňte kód XML, který se zobrazí v podokně šablony manifestu.  
  
     Změny v souboru XML se zobrazí v **ve verzi Preview ze zabalené Manifest** podokně.  
  
## <a name="overwrite-the-packaged-manifest-file"></a>Přepsání souboru manifestu balíčku  
 Můžete zakázat funkce návrháře a vytvořit *feature.xml* soubor ručně. Při prvním provedení tohoto postupu, aktuální nastavení v Návrháři funkce se ukládají do souboru XML šablony funkce. Potom můžete upravit nebo přepsat kód XML.  
  
> [!NOTE]  
>  Je-li přidat nebo odebrat položky Sharepointového projektu v souboru XML, Designer funkce je zakázáno, tyto položky projektu nejsou zabaleny.  
  
#### <a name="to-overwrite-packaged-manifest-file-by-disabling-the-designer"></a>K přepsání souboru manifestu balíčku zakázáním návrháře  
  
1.  V **návrháře funkcí**, zvolte **Manifest** kartu.  
  
2.  Rozbalte **upravit možnosti** uzlu, vyberte **přepsat vygenerovaný kód XML a upravit manifest v editoru XML** propojit a klikněte na tlačítko **Ano** tlačítko.  
  
     Šablona se aktualizuje aktuální soubor manifestu balíčku.  
  
## <a name="enable-the-feature-designer"></a>Povolení funkce návrháře  
 Můžete znovu povolit funkci návrháři si můžete přizpůsobit *feature.xml* souboru.  
  
#### <a name="to-re-enable-the-designer"></a>Chcete-li znovu povolí návrháře  
  
1.  V **návrháře funkcí**, zvolte **zahodit úpravy manifestu a znovu povolí návrháře** propojit a klikněte na tlačítko **Ano** tlačítko.  
  
2.  Šablona se aktualizuje s původním textem a budou ztraceny všechny změny do souboru XML.  
  
## <a name="see-also"></a>Viz také:
 [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
