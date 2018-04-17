---
title: 'Postupy: Přidání vlastnosti do projektů služby SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- projects [SharePoint development in Visual Studio], extending
- SharePoint development in Visual Studio, extending projects
- SharePoint projects, extending
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: fe3b94d7f2072565b2adc2ab7c3c9825ca21ad57
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-a-property-to-sharepoint-projects"></a>Postupy: Přidání vlastnosti do projektů služby SharePoint
  Přidání vlastnosti do jakéhokoli projektu služby SharePoint můžete použít rozšíření projektu. Vlastnost se zobrazí v **vlastnosti** okno, pokud je vybrána projektu v **Průzkumníku řešení**.  
  
 Následující postup předpokládá, že jste již vytvořili rozšíření projektu. Další informace najdete v tématu [postupy: vytváření rozšíření projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md).  
  
### <a name="to-add-a-property-to-a-sharepoint-project"></a>Přidání vlastnosti do projektu služby SharePoint  
  
1.  Definice třídy s veřejnou vlastnost, která reprezentuje vlastnost, kterou chcete přidat do projektů služby SharePoint. Pokud chcete přidat více vlastností, můžete definovat všechny vlastnosti v stejné třídy nebo různých tříd.  
  
2.  V <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> metodu vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> implementace, popisovač <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectPropertiesRequested> události *projectService* parametr.  
  
3.  V obslužné rutiny události pro <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectPropertiesRequested> událostí, přidejte instance třídy vlastnosti k <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectPropertiesRequestedEventArgs.PropertySources%2A> kolekce parametru argumentů události.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak přidat dvě vlastnosti do projektů služby SharePoint. Jednu vlastnost dál jeho data v souboru projektu uživatele možnost (. soubor csproj.user nebo. vbproj.user souboru). Ostatní vlastnosti dál jeho data v souboru projektu (souboru .csproj nebo .vbproj soubor).  
  
 [!code-vb[SpExt_SPCustomPrjProperty#1](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#1)]
 [!code-csharp[SpExt_SPCustomPrjProperty#1](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#1)]  
  
### <a name="understanding-the-code"></a>Pochopení kódu  
 Zajistit, aby stejnou instanci systému `CustomProjectProperties` třída se používá pokaždé, když <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectPropertiesRequested> dojde k události, příklad kódu přidá vlastnosti objekt, který má <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnost projektu první, když dojde k této události. Kód načte tento objekt vždy, když dojde znovu k této události. Další informace o používání <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnost pro přidružení dat s projekty, najdete v části [přidružení vlastních dat k rozšíření nástrojů SharePoint](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).  
  
 K zachování změn hodnot vlastností **nastavit** přistupující objekty pro vlastnosti, použijte následující rozhraní API:  
  
-   `CustomUserFileProperty` používá <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.ProjectUserFileData%2A> vlastnost, která má v souboru projektu uživatele možnost uložte jeho hodnotu.  
  
-   `CustomProjectFileProperty` používá <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetPropertyValue%2A> metoda uložení jeho hodnoty do souboru projektu.  
  
 Další informace o zachování data v těchto souborech najdete v tématu [ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
### <a name="specifying-the-behavior-of-custom-properties"></a>Určení chování vlastní vlastnosti  
 Můžete definovat jak vlastní vlastnosti se zobrazí a chovají v **vlastnosti** okna s použitím atributů z <xref:System.ComponentModel> obor názvů pro definování vlastnosti. Následující atributy jsou užitečné v mnoha scénářích:  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>: Určuje název vlastnosti, které se zobrazí v **vlastnosti** okno.  
  
-   <xref:System.ComponentModel.DescriptionAttribute>: Určuje popis řetězec, který se zobrazí v dolní části **vlastnosti** okno, pokud je vybrána vlastnost.  
  
-   <xref:System.ComponentModel.DefaultValueAttribute>: Určuje výchozí hodnotu vlastnosti.  
  
-   <xref:System.ComponentModel.TypeConverterAttribute>: Určuje vlastní převod mezi řetězec, který se zobrazí v **vlastnosti** okno a hodnotu vlastnosti jiné než řetězec.  
  
-   <xref:System.ComponentModel.EditorAttribute>: Určuje vlastní editor k úpravě vlastnost.  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   Microsoft.VisualStudio.Shell  
  
-   Microsoft.VisualStudio.Shell.Interop  
  
-   Microsoft.VisualStudio.Shell.Interop.8.0  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Nasazení rozšíření  
 Chcete-li nasadit rozšíření, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení a všechny další soubory, které chcete distribuovat s rozšířením. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření projektů SharePoint](../sharepoint/extending-sharepoint-projects.md)   
 [Postupy: vytváření rozšíření projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md)   
 [Postupy: Přidání položky místní nabídky do projektů služby SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md)   
 [Rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)  
  
  