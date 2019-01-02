---
title: Uložení dat do rozšíření systému projektu služby SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
helpviewer_keywords:
- SharePoint project items, saving string data
- project items [SharePoint development in Visual Studio], saving string data
- projects [SharePoint development in Visual Studio], saving string data
- SharePoint projects, saving string data
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c7f0210a24df180e93aa8772f08b91e7312f5ccc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53829247"
---
# <a name="save-data-in-extensions-of-the-sharepoint-project-system"></a>Ukládání dat do rozšíření systému projektu služby SharePoint
  Když rozšíříte systému Sharepointových projektů, můžete uložit data řetězce, který bude zachován po zavření projektu služby SharePoint. Data jsou obvykle související s položkou konkrétního projektu nebo pomocí samotného projektu.  
  
 Pokud máte data, která není potřeba zachovat, můžete přidat data do libovolného objektu v objektovém modelu serveru SharePoint nástroje, který implementuje <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject> rozhraní. Další informace najdete v tématu [rozšíření nástrojů přidružení vlastních dat se Sharepointem](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).  
  
## <a name="save-data-that-is-associated-with-a-project-item"></a>Uložit data, která je přidružená k položce projektu
 Pokud máte data, která je přidružený k určité položky projektu služby SharePoint, jako je například hodnota vlastnosti, které přidáte do položky projektu, můžete uložit data, která mají *.spdata* souboru pro položku projektu. Chcete-li to provést, použijte <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> vlastnost <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> objektu. Data, která přidáte do této vlastnosti se ukládají **ExtensionData –** prvek *.spdata* souboru pro položku projektu. Další informace najdete v tématu [ExtensionData – Element](../sharepoint/extensiondata-element.md).  
  
 Následující příklad kódu ukazuje, jak používat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> vlastnost k uložení hodnoty vlastnosti typu string, který je definován v vlastního typu položky projektu služby SharePoint. Tento příklad v rámci většího příkladu najdete v tématu [jak: Přidání vlastnosti do vlastního typu položky projektu SharePoint](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md).  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#14](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypeproperty.vb#14)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#14](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypeproperty.cs#14)]  
  
## <a name="save-data-that-is-associated-with-a-project"></a>Ukládání dat, který je spojen s projektem
 Až budete mít data na úrovni projektu, jako je například hodnota vlastnosti, které přidáte do projektů služby SharePoint, můžete data uložit do souboru projektu ( *.csproj* souboru nebo *.vbproj* souboru), nebo možnost uživatele projektu soubor ( *. csproj.user* souboru nebo *. vbproj.user* souboru). Soubor, který můžete uložit data v závisí na způsobu dat, který se má použít:  
  
-   Pokud chcete data, která mají být dostupné pro všechny vývojáře, kteří spustí projektu služby SharePoint, uložte data do souboru projektu. Tento soubor je vždy změnami do zdrojové databáze ovládací prvek, takže data v tomto souboru jsou k dispozici s ostatními vývojáři, kteří projekt rezervovat.  
  
-   Pokud chcete data, která mají být k dispozici pouze pro aktuální vývojář, který má SharePoint projekt otevřít v sadě Visual Studio, uložte tato data do možnost uživatelského souboru projektu. Tento soubor se změnami obvykle do zdrojové databáze ovládacího prvku, tak data v tomto souboru nejsou k dispozici s ostatními vývojáři, kteří projekt rezervovat.  
  
### <a name="save-data-to-the-project-file"></a>Ukládání dat do souboru projektu
 K ukládání dat do souboru projektu, převést <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> a poté pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetPropertyValue%2A> metoda. Následující příklad kódu ukazuje, jak použít tuto metodu pro uložení hodnoty vlastnosti projektu do souboru projektu. Tento příklad v rámci větší ukázky najdete v tématu [jak: Přidání vlastnosti do projektů služby SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md).  
  
 [!code-vb[SpExt_SPCustomPrjProperty#3](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#3)]
 [!code-csharp[SpExt_SPCustomPrjProperty#3](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#3)]  
  
 Další informace o převodu <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objekty na jiné typy v modelu objektu automatizace sady Visual Studio nebo integrace objektový model, najdete v článku [převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md).  
  
### <a name="save-data-to-the-project-user-option-file"></a>Ukládání dat do možnost uživatelského souboru projektu
 Chcete-li uložit data do možnost uživatelského souboru projektu, použijte <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.ProjectUserFileData%2A> vlastnost <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> objektu. Následující příklad kódu ukazuje, jak pomocí této vlastnosti lze uložit hodnotu vlastnosti projektu možnost uživatelského souboru projektu. Tento příklad v rámci větší ukázky najdete v tématu [jak: Přidání vlastnosti do projektů služby SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md).  
  
 [!code-vb[SpExt_SPCustomPrjProperty#2](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#2)]
 [!code-csharp[SpExt_SPCustomPrjProperty#2](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#2)]  
  
## <a name="see-also"></a>Viz také:
 [Rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)   
 [Přidružení vlastních dat k rozšíření nástrojů SharePoint](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)   
 [Převod mezi systémovými typy projektů SharePoint a jinými typy projektů Visual Studio](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)  
