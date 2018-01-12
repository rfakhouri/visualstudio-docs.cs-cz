---
title: "Primární spolupracující sestavení Office | Microsoft Docs"
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
- primary interop assemblies
- assemblies [Office development in Visual Studio], primary interop assemblies
- Office primary interop assemblies
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 906100a572170f218a23b1887ab7fddee37251b9
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="office-primary-interop-assemblies"></a>Sestavení primární spolupráce sady Office
  Pokud chcete používat funkce aplikace Microsoft Office z projektu aplikace Office, musíte použít primární spolupracující sestavení (PIA) pro aplikaci. PRIMÁRNÍ povoluje spravovaného kódu k interakci s modelem COM na objekt z aplikace Microsoft Office.  
  
 Když vytvoříte nový projekt Office, Visual Studio přidá odkazy na PIA, které jsou nutné k sestavení projektu. V některých scénářích může být nutné přidat odkazy na další PIA (například pokud chcete použít funkci Microsoft Office Word v projektu pro aplikaci Microsoft Office Excel).  
  
 Toto téma popisuje následující aspekty pomocí Microsoft Office PIA v projektech Office:  
  
-   [Samostatný primární spolupracující sestavení pro vytváření a spouštění projektů](#separateassemblies)  
  
-   [Pomocí funkce více aplikace Microsoft Office v jednom projektu](#usingfeatures)  
  
-   [Úplný seznam primárních sestavení vzájemné spolupráce pro aplikace Microsoft Office](#pialist)  
  
 Další informace o primární spolupracující sestavení najdete v tématu [primární zprostředkovatel komunikace s objekty sestavení](http://msdn.microsoft.com/en-us/b977a8be-59a0-40a0-a806-b11ffba5c080).  
  
##  <a name="separateassemblies"></a>Jednotlivé primární spolupracující sestavení pro vytváření a spouštění projektů  
 Visual Studio využívá různé sady PIA na vývojovém počítači. Tyto různé sady sestavení jsou v následujících umístěních:  
  
-   Do složky v adresáři program files.  
  
     Tyto kopie sestavení se používají při psaní kódu a sestavení projektů. Visual Studio automaticky nainstaluje tyto sestavení.  
  
-   Globální mezipaměti sestavení.  
  
     Tyto kopie sestavení se používají při některých úloh vývoj, například při spuštění nebo ladění projektů. Visual Studio nepodporuje instalaci a registraci tyto sestavení; je potřeba udělat sobě.  
  
### <a name="primary-interop-assemblies-in-the-program-files-directory"></a>Primární spolupracující sestavení v adresáři Program Files  
 Při instalaci sady Visual Studio PIA automaticky nainstalují do umístění v systému souborů, mimo globální mezipaměti sestavení. Při vytváření nového projektu sady Visual Studio automaticky přidá reference na tyto kopie PIA do projektu. Visual Studio použije tyto kopie PIA, místo sestavení v globální mezipaměti sestavení, chcete-li vyřešit odkazy na typ při vývoji a sestavení projektu.  
  
 Tyto kopie PIA pomoci vyhnout několik vývoj problémů, které může dojít, když jsou různé verze PIA zaregistrovaný v globální mezipaměti sestavení sady Visual Studio.  
  
 Visual Studio nainstaluje tyto kopie PIA do následujícího umístění na vývojovém počítači:  
  
-   %ProgramFiles%\Microsoft visual Studio 12.0\Visual Studio nástroje pro Office\PIA\Office14  
  
     (nebo % ProgramFiles (x86) %\Microsoft Visual Studio 12.0\Visual Studio Tools for Office\PIA\Office14 na 64bitové operační systémy)  
  
-   %ProgramFiles%\Microsoft visual Studio 12.0\Visual Studio nástroje pro Office\PIA\Office15  
  
     (nebo % ProgramFiles (x86) %\Microsoft Visual Studio 12.0\Visual Studio Tools for Office\PIA\Office15 na 64bitové operační systémy)  
  
### <a name="primary-interop-assemblies-in-the-global-assembly-cache"></a>Primární spolupracující sestavení v globální mezipaměti sestavení  
 K provedení některých úkolů vývoj, musí být nainstalované PIA a zaregistrován v globální mezipaměti sestavení na vývojovém počítači. Obvykle PIA instalují automaticky při instalaci Office na vývojovém počítači. Další informace najdete v tématu [Konfigurace počítače pro vývoj řešení pro Office](../vsto/configuring-a-computer-to-develop-office-solutions.md).  
  
 PIA Office nejsou na počítačích koncových uživatelů se vyžaduje spuštění řešení pro systém Office. Další informace najdete v tématu [návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md).  
  
##  <a name="usingfeatures"></a>Pomocí funkce více aplikace Microsoft Office v jednom projektu  
 Šablona projektu každých Office v sadě Visual Studio je navržen pro práci s jednu aplikaci Microsoft Office. Použití funkcí v několika aplikace Microsoft Office, nebo chcete používat funkce aplikace nebo součásti, která nemá na projekt v sadě Visual Studio, je nutné přidat odkaz na požadované PIA.  
  
 Ve většině případů měli byste přidat odkazy na PIA, které jsou nainstalované ve Visual Studio v části %ProgramFiles%\Microsoft Visual Studio 12.0\Visual Studio Tools pro Office\PIA\ adresář. Tyto verze sestavení se zobrazí na **Framework** kartě **Manager odkaz** dialogové okno. Další informace najdete v tématu [postup: cíl aplikací prostřednictvím primární zprostředkovatel komunikace s objekty sestavení sady Office](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md).  
  
 Pokud máte nainstalovaný a zaregistrovaný PIA v globální mezipaměti sestavení, tyto verze sestavení zobrazí na **COM** kartě **správce odkazů** dialogové okno. Neměli byste přidávání odkazů na tyto verze sestavení, protože existují některé problémy vývoj, které můžou nastat, když je budete používat. Například pokud různé verze PIA je zaregistrovaný v globální mezipaměti sestavení, projekt bude automaticky navážou na verze sestavení, který byl zaregistrován poslední – i v případě, že jste zadali na jinou verzi sestavení  **COM** kartě **správce odkazů** dialogové okno.  
  
> [!NOTE]  
>  Některá sestavení se přidají do projektu automaticky při přidání sestavení, které na ně odkazuje. Odkazy na sestavení Office.dll a Microsoft.Vbe.Interop.dll například se automaticky přidá, když přidáte odkaz na sestavení aplikace Word, Excel, Outlook, Microsoft Forms nebo grafu.  
  
##  <a name="pialist"></a>Primární spolupracující sestavení pro aplikace Microsoft Office  
 Následující tabulka uvádí primární spolupracující sestavení, které jsou k dispozici pro [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] a [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)].  
  
|Aplikace Office nebo součást|Název sestavení primární spolupráce|  
|-------------------------------------|-----------------------------------|  
|Aplikace Microsoft Access 14.0 objektu knihovny<br /><br /> Aplikace Microsoft Access 15.0 objektu knihovny|Microsoft.Office.Interop.Access.dll|  
|Aplikace Microsoft Office 14.0 přístup k databázi modul objektu knihovny<br /><br /> Aplikace Microsoft Office 15.0 přístup k databázi modul objektu knihovny|Microsoft.Office.Interop.Access.Dao.dll|  
|Aplikace Microsoft Excel 14.0 objektu knihovny<br /><br /> Aplikace Microsoft Excel 15.0 objektu knihovny|Microsoft.Office.Interop.Excel.dll|  
|Microsoft Graph 14.0 objektu knihovny (používá se tím, PowerPoint, Word a přístup pro grafy)<br /><br /> Microsoft Graph 15.0 objektu knihovny|Microsoft.Office.Interop.Graph.dll|  
|Knihovny typů pro aplikaci Microsoft InfoPath 2.0 (pro pouze InfoPath 2007)|Microsoft.Office.Interop.InfoPath.dll|  
|Microsoft InfoPath XML spolupráce sestavení (pro pouze InfoPath 2007)|Microsoft.Office.Interop.InfoPath.Xml.dll|  
|Microsoft Office 14.0 objektu knihovny (Office sdílené funkce)<br /><br /> Microsoft Office 15.0 objektu knihovny (Office sdílené funkce)|Office.dll|  
|Microsoft Office Outlook zobrazení ovládacího prvku (můžete použít na webové stránky a v aplikacích pro přístup k vaší doručené poště)|Microsoft.Office.Interop.OutlookViewCtl.dll|  
|Aplikace Microsoft Outlook 14.0 objektu knihovny<br /><br /> Aplikace Microsoft Outlook 15.0 objektu knihovny|Microsoft.Office.Interop.Outlook.dll|  
|Microsoft PowerPoint 14.0 objektu knihovny<br /><br /> Microsoft PowerPoint 15.0 objektu knihovny|Microsoft.Office.Interop.PowerPoint.dll|  
|Aplikace Microsoft Project 14.0 objektu knihovny<br /><br /> Aplikace Microsoft Project 15.0 objektu knihovny|Microsoft.Office.Interop.MSProject.dll|  
|Aplikaci Microsoft Publisher 14.0 objektu knihovny<br /><br /> Aplikaci Microsoft Publisher 15.0 objektu knihovny|Microsoft.Office.Interop.Publisher.dll|  
|Microsoft SharePoint Designer 14.0 webové objektu Reference knihovny|Microsoft.Office.Interop.SharePointDesigner.dll|  
|Microsoft SharePoint Designer 14.0 stránky objektu Reference knihovny|Microsoft.Office.Interop.SharePointDesignerPage.dll|  
|Knihovny typů 2.0 inteligentní značky Microsoft **Poznámka:** inteligentní značky nepoužívají v [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] a [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].|Microsoft.Office.Interop.SmartTag.dll|  
|Aplikace Microsoft Visio 14.0 knihovny typů<br /><br /> Aplikace Microsoft Visio 15.0 knihovny typů|Microsoft.Office.Interop.Visio.dll|  
|Aplikace Microsoft Visio 14.0 uložit jako webové knihovny typů<br /><br /> Aplikace Microsoft Visio 15.0 uložit jako webové knihovny typů|Microsoft.Office.Interop.Visio.SaveAsWeb.dll|  
|Aplikace Microsoft Visio 14.0 vykreslování ovládacího prvku typu knihovny<br /><br /> Aplikace Microsoft Visio 15.0 vykreslování ovládacího prvku typu knihovny|Microsoft.Office.Interop.VisOcx.dll|  
|Aplikace Microsoft Word 14.0 objektu knihovny<br /><br /> Aplikace Microsoft Word 15.0 objektu knihovny|Microsoft.Office.Interop.Word.dll|  
|Microsoft Visual Basic for Applications – rozšiřitelnost 5.3|Microsoft.Vbe.Interop.dll|  
  
### <a name="binding-redirect-assemblies"></a>Sestavení přesměrování vazby  
 Při instalaci a registraci Office PIA v globální mezipaměti sestavení (buď v sadě Office nebo instalací redistribuovatelného balíčku pro PIA), přesměrování vazby sestavení jsou také nainstalované jenom v globální mezipaměti sestavení. Tyto sestavení pomoci, ujistěte se, zda jsou načteny správnou verzi primární spolupracující sestavení za běhu. Například když řešení, který odkazuje [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] sestavení běží na počítači, který má [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] dá pokyn přesměrování vazby sestavení verze stejného sestavení primární spolupráce [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)] runtime k načtení [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] verze sestavení primární spolupráce. Další informace najdete v tématu [postupy: povolení a zakázání automatického přesměrování vazby](/dotnet/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: cílení na aplikace Office prostřednictvím primární spolupráce – sestavení](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md)   
 [Řešení pro aplikaci InfoPath](../vsto/infopath-solutions.md)   
 [Přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md)   
 [Řešení pro aplikaci PowerPoint](../vsto/powerpoint-solutions.md)   
 [Projektová řešení](../vsto/project-solutions.md)   
 [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)   
 [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)   
 [Obecné referenční informace &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/general-reference-office-development-in-visual-studio.md)  
  
  