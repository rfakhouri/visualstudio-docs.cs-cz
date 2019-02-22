---
title: Šablony podpory webu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- we site projects, templates
ms.assetid: 37173c97-486b-4b3c-8ed3-cf5890c4de23
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 75e918c752484129f9b89f939bc6fbbce6df803c
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56618195"
---
# <a name="web-site-support-templates"></a>Šablony podpory webu
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Šablony projektů a položek webu poskytují opakovaně použitelných a přizpůsobitelné webové stránky projektů a položek zástupné procedury, které zrychlení procesu vývoje tak, že odeberete potřebu vytvářet nové webových projektů a položek od začátku. Další informace o [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] šablony, najdete v článku [vytváření projektů a šablon položek](../../ide/creating-project-and-item-templates.md).

## <a name="project-template-folder"></a>Složka šablony projektu
 Šablony webových projektů se obvykle instalují na [*Visual Studio Instalační cesta*] \Common7\IDE\ProjectTemplates\Web\\, každého do podsložky, která má stejný název webu programovací jazyk.

## <a name="project-file"></a>Soubor projektu
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Integrované vývojové prostředí (IDE) vyžaduje příponu souboru projektu jako způsob, jak namapovat na správný projekt typu šablony. Protože webové projekty není nutné soubor projektu, .webproj fiktivní projektu soubor rozšíření je zaregistrovaný k mapování šablonu typu projektu.

 Řetězec názvu jazykové Volitelně lze přidat do šablony, aby systém webového projektu, chcete-li nastavit výchozí jazyk **přidat novou položku** dialogové okno pro položky na základě šablony. Řetězec musí obsahovat první řádek souboru. Musí odpovídat názvu zaregistrován AddItemLanguageName registraci modulu technologie IntelliSense v i název zaregistrován Subtype(VsTemplate) projektu. Další informace najdete v tématu [atributy podpory webu](../../extensibility/internals/web-site-support-attributes.md).

 Pokud řetězec není k dispozici, systém webového projektu se pokusí určit výchozí jazyk podle jazyková rozšíření atribut a soubor stránek do webového projektu pomocí šablony projektu.

## <a name="project-templates"></a>Šablony projektů
 Šablony projektů webu se používají k vytváření nových webů v reakci na **nový web** příkaz **souboru** nabídky. Aktuálně jsou podporovány tři typy projektů webu:

-   Prázdný web webové projekty

-   Webové projekty

-   Projekty webových služeb

### <a name="empty-web-site-projects"></a>Prázdný web webové projekty
 Tyto soubory vytvořit nový prázdný web v reakci **prázdný web** příkaz, který je k dispozici po výběru **souboru** > **nový web**:

-   EmptyWeb.vstemplate

     Soubor šablony, který provede vytvoření nového prázdného webu.

-   EmptyWeb.webproj

     Tento soubor je systém šablony projektu. Odkaz na soubor projektu v souboru EmptyWeb.vstemplate splňuje.

### <a name="web-site-projects"></a>Webové projekty
 Tyto soubory vytvořit novou webovou stránku v reakci na **Web ASP.NET s** příkaz, který je k dispozici po výběru **souboru** > **nový web**:

-   Default.aspx

     Výchozí domovskou stránku pro nový web. Atribut Language Určuje jazyk codebehind a určuje Atribut CodeFile závislého souboru, který obsahuje kód codebehind přidružený k této stránce.

-   Default.aspx. *rozšíření*

     Závislý soubor, který obsahuje kód codebehind výchozí domovskou stránku. Určuje jazyk codebehind *rozšíření* tohoto souboru.

-   web.config

     Kořenové web.site konfigurační soubor.

-   WebApplication.vstemplate

     Soubor šablony, který zjistí obsah webu řešení a vynutí vytvoření souboru složce App_Data.

-   WebApplication.webproj

     Tento soubor je systém šablony projektu. Odkaz na soubor projektu v souboru WebApplication.vstemplate splňuje.

### <a name="web-service-projects"></a>Projekty webových služeb
 Tyto soubory vytvořit novou webovou stránku v reakci na **webová služba ASP.NET** příkaz, který je k dispozici po výběru **souboru** > **nový web**:

-   Service.asmx

     Na stránce HTML pro nové webové služby. Atribut Language Určuje jazyk codebehind a určuje atribut CodeBehind závislého souboru, který obsahuje codebehind kód spojený s touto službou.

-   Služba. *Rozšíření*

     Závislý soubor, který implementuje třídu služby. Určuje jazyk codebehind *rozšíření* tohoto souboru.

-   web.config

-   Kořenové web.site konfigurační soubor.

-   WebService.vstemplate

     Soubor šablony, který zjistí obsah webu řešení a vynutí vytvoření složky App_Data a App_Code. Služba. *rozšíření* soubor je zkopírován do složky App_Code.

-   WebService.webproj

     Tento soubor je systém šablony projektu. Odkaz na soubor projektu v souboru WebService.vstemplate splňuje.

## <a name="project-item-template-folder"></a>Složky šablony položky projektu
 Webové šablony položky projektu se obvykle instalují do [*Visual Studio Instalační cesta*] \Common7\IDE\ItemTemplates\Web\\, každou v podsložce s názvem po jeho web programovací jazyk.

## <a name="project-item-templates"></a>Šablony položek projektu
 Šablony položek projektu webové stránky se používají k přidání nové webové stránky pro webovou stránku v reakci **přidat existující položku** příkazu. Aktuálně jsou podporovány tyto druhy webové stránky:

-   Nová třída

-   Nová stránka HTML

-   Nový webový formulář

-   Nová stránka předlohy

### <a name="new-class"></a>Nová třída
 Tato šablona vytvoří nového zdrojového souboru, který definuje prázdnou třídu v reakci **přidejte novou třídu** příkazu.

-   Třída. *Rozšíření*

     Zdrojový soubor, který implementuje prázdnou třídu. Určuje jazyk codebehind *rozšíření* tohoto souboru.

-   Class.vstemplate

     Soubor šablony, která vytvoří zdrojový soubor a určuje jeho obsah.

### <a name="new-html-page"></a>Nová stránka HTML
 Tato šablona vytvoří novou webovou stránku v reakci **přidejte novou stránku HTML** příkazu.

-   HTMLPage.htm

     Výchozí obsah webové stránky. Tato webová stránka obvykle nemá žádný přidružený codebehind závislý soubor. Vytvořit stránku inteligentní souborem přidružené codebehind, použijte šablonu Webový formulář.

-   HTMLPage.vstemplate

     Soubor šablony, která vytvoří webovou stránku a určuje jeho obsah.

### <a name="new-webform"></a>Nový webový formulář
 Tato šablona vytvoří novou inteligentní webovou stránku v reakci **přidat nový webový formulář** příkazu.

 Chcete-li vytvořit závislé codebehind zdrojový soubor, vyberte **umístěte kód v samostatném souboru**. Jediné webové stránky v opačném případě se vytvoří, který má prázdný skriptovací bloku a ne \<stránky % > direktivy propojení závislého souboru.

 Chcete-li vytvořit stránku obsahu pro vybranou stránku předlohy, vyberte **vyberte stránku předlohy**.

-   WebForm.aspx

     Výchozí obsah webové stránky. Tato webová stránka nemá žádný přidružený codebehind závislý soubor.

-   WebForm_cb.aspx

     Výchozí obsah webové stránky. Tato webová stránka má závislý soubor přidružené codebehind.

-   CodeBehind. *Rozšíření*

     Závislý soubor, který implementuje třídu webového formuláře. Určuje jazyk codebehind *rozšíření* tohoto souboru.

-   ContentPage.aspx

     Výchozí obsah webové stránky jako stránku obsahu. Tato webová stránka nemá žádný přidružený codebehind závislý soubor.

-   ContentPage_cb.aspx

     Výchozí obsah webové stránky jako stránku obsahu. Tato webová stránka má závislý soubor přidružené codebehind.

-   WebForm.vstemplate

     Soubor šablony, která určuje obsah nové webové stránky a jeho závislých souborů, pokud existuje.

### <a name="new-master-page"></a>Nová stránka předlohy
 Tato šablona vytvoří novou stránku předlohy v reakci **přidejte novou stránku předlohy** příkazu.

 Chcete-li vytvořit závislé codebehind zdrojový soubor, vyberte **umístěte kód v samostatném souboru**. Jediné webové stránky v opačném případě se vytvoří, který má prázdný skriptovací bloku a ne \<stránky % > direktivy propojení závislého souboru.

-   MasterPage.master

     Výchozí obsah stránky předlohy. Tato stránka předlohy nemá žádný soubor závislé přidružené codebehind.

-   MasterPage_cb.master

     Výchozí obsah stránky předlohy. Tato hlavní stránka má závislý soubor přidružené codebehind.

-   CodeBehind. *rozšíření*

     Závislý soubor, který implementuje třídu stránky předlohy. Určuje jazyk codebehind *rozšíření* tohoto souboru.

-   MasterPage.vstemplate

     Soubor šablony, která určuje obsah nové stránky předlohy a jeho závislých souborů, pokud existuje.

## <a name="see-also"></a>Viz také
- [Podpora webu](../../extensibility/internals/web-site-support.md)