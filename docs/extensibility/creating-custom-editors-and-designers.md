---
title: "Vytváření vlastních editory a návrháři | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- designers [Visual Studio SDK]
- editors [Visual Studio SDK], custom
ms.assetid: b6a5e8b2-0ae1-4fc3-812d-09d40051b435
caps.latest.revision: "31"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d8d354333545a6ec2b637e160818d506fa049c29
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="creating-custom-editors-and-designers"></a>Vytváření vlastních editory a návrhářů
Integrované vývojové prostředí (IDE) sady Visual Studio může hostovat různé typy editoru:  
  
-   Základní editoru Visual Studio  
  
-   Vlastní editory  
  
-   Externí editory  
  
-   Návrháři  
  
 Následující informace vám umožňuje vybrat typ editor, které potřebujete.  
  
## <a name="types-of-editor"></a>Typy editoru  
 Informace o základní editoru Visual Studio najdete v tématu [rozšíření pro Editor a služby, jazyk](../extensibility/extending-the-editor-and-language-services.md).  
  
##### <a name="custom-editors"></a>Vlastní editory  
 Vlastní editor je ten, který je navržen pro práci v specializované případech. Například může vytvořit editoru, jejichž funkcí je číst a zapisovat data do konkrétní úložiště, jako je Microsoft Exchange server. Pokud chcete editor, který funguje s vašeho projektu typu nebo pokud chcete, aby editor, který má jenom pár určité příkazy, zvolte vlastní editor. Upozorňujeme však, že uživatelé nebudou moci používat vlastní editor upravit standard [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projekty.  
  
 Vlastní editor můžete použít objekt factory editoru a přidat informace o Editoru registru. Typ projektu přidružené vlastního editoru můžete vytvořit instanci vlastního editoru jinými způsoby.  
  
 Vlastní editor můžete použít buď aktivace na místě nebo zjednodušené vložení k implementaci zobrazení.  
  
##### <a name="external-editors"></a>Externí editory  
 Externí editory jsou editory, které nejsou součástí Visual Studio, jako je například Microsoft Word, Poznámkový blok nebo Microsoft FrontPage. Pokud například jsou předávání textu do ní z vaší VSPackage můžete volat takové editoru. Externí editory lze použít mimo Visual Studio se registrují. Když zavoláte externího editoru a lze jej vkládat v okně hostitele, pak zobrazí se v okně v prostředí IDE. Pokud ne, pak rozhraní IDE vytvoří pro ni samostatném okně.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> Metoda nastaví prioritu dokumentu pomocí <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> výčtu. Pokud `DP_External` je zadána hodnota, soubor lze otevřít v externím editoru.  
  
## <a name="editor-design-decisions"></a>Rozhodnutí o návrhu editoru  
 Následující dotazy týkající se návrhu vám pomůže vybrat typ editor nejlepší vhodné k vaší aplikaci:  
  
-   Bude vaše aplikace uložit svá data v souborech nebo ne? Pokud ji bude ukládat data v souborech, že bude ve formátu vlastní nebo standardní?  
  
     Pokud použijete standardní formát souboru, bude moct otevírat a pro čtení a zápis dat do nich typy projektu kromě projektu. Pokud používáte vlastní formát, bude moct otevírat a čtení nebo zápisu dat do je však pouze typ vašeho projektu.  
  
     Pokud váš projekt používá soubory, pak byste měli stránku upravit standardního editoru. Pokud váš projekt soubory nepoužívá, ale spíš používá položky v databázi nebo jiné úložiště, měli byste vytvořit vlastní editor.  
  
-   Potřebuje vaše editor k hostování ovládacích prvků ActiveX?  
  
     Pokud vaše editor hostuje ovládací prvky ActiveX, editoru aktivace na místě, jak je uvedeno v pak implementovat [aktivace na místě](../extensibility/in-place-activation.md). Pokud není hostitelem – ovládací prvky ActiveX, potom použijte zjednodušené vnoření editor nebo přizpůsobit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] výchozí editor.  
  
-   Bude vaše editor podporovat více zobrazení? Pokud chcete, aby zobrazení vaší editoru mají být zobrazeny ve stejnou dobu jako výchozí editor, musí podporovat více zobrazení.  
  
     Pokud vaše editor potřebuje zajistit podporu více zobrazení, musí být dokument data a objekty zobrazení dokumentu pro editor samostatné objekty. Další informace najdete v tématu [podpora více zobrazení dokumentu](../extensibility/supporting-multiple-document-views.md).  
  
     Pokud vaše editor podporuje více zobrazení, máte v úmyslu použít [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] základní implementace vyrovnávací paměti na editoru textu (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objekt) pro data objektu dokumentu? To znamená, že chcete pro podporu vašeho editor zobrazení-souběžného s [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] editor jádra? Možnost k tomu je základem Návrhář formulářů...  
  
-   Pokud potřebujete k hostování externího editoru, můžete editoru vložit do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]?  
  
     Pokud lze jej vkládat, by měl vytvořit okno hostitele pro externí editor a pak zavolají <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> metoda a sadu <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> hodnotu výčtu `DP_External`. Jestliže editoru nelze vložit, rozhraní IDE samostatném okně automaticky vytvoří pro ni.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Návod: Vytvoření vlastního editoru](../extensibility/walkthrough-creating-a-custom-editor.md)  
 Vysvětluje, jak vytvořit vlastní editor.  
  
 [Návod: Přidání funkcí do vlastního editoru](../extensibility/walkthrough-adding-features-to-a-custom-editor.md)  
 Vysvětluje, jak pro přidání funkcí do vlastní editor.  
  
 [Inicializace návrháře a konfigurace metadat](../extensibility/designer-initialization-and-metadata-configuration.md)  
 Vysvětluje, jak k chybě při inicializaci návrháře.  
  
 [Nastavení podpory fáze vrácení zpět v návrháři](../extensibility/supplying-undo-support-to-designers.md)  
 Vysvětluje, jak zajistit podporu vrácení zpět pro návrháře.  
  
 [Barevné zvýrazňování syntaxe ve vlastních editorech](../extensibility/syntax-coloring-in-custom-editors.md)  
 Vysvětluje rozdíl mezi v editoru základní a vlastní editory zvýrazňování syntaxe.  
  
 [Data dokumentu a zobrazení dokumentu ve vlastních editorech](../extensibility/document-data-and-document-view-in-custom-editors.md)  
 Vysvětluje, jak implementovat vlastní editory data dokumentů a zobrazení dokumentu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Starší verze rozhraní v editoru](../extensibility/legacy-interfaces-in-the-editor.md)  
 Vysvětluje, jak pro přístup k editoru základní prostřednictvím starší verze rozhraní API.  
  
 [Vývoj služby starší verze jazyka](../extensibility/internals/developing-a-legacy-language-service.md)  
 Vysvětluje, jak implementovat služba jazyka.  
  
 [Rozšíření dalších částí sady Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md)  
 Vysvětluje, jak vytvářet prvky uživatelského rozhraní, které odpovídají zbytek [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>