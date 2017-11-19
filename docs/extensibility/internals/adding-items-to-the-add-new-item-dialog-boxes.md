---
title: "Přidávání položek do pro přidání nové položky dialogových oken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Add New Item dialog box, adding items
ms.assetid: 2f70863b-425b-4e65-86b4-d6a898e29dc7
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5a16698863e92e5bbae4e888502788dd76b04f56
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="adding-items-to-the-add-new-item-dialog-boxes"></a>Přidávání položek do pro přidání nové položky dialogových oken
Proces přidávání položek do **přidat novou položku** dialogové okno začíná klíče registru. Jak ukazuje následující položky registru, obsahuje cestu a název adresáře, ve které položky k dispozici v části AddItemTemplates **přidat novou položku** daly dialogové okno.  
  
> [!NOTE]
>  Tabulka hned za segment kódu obsahuje další informace o položku registru.  
  
 V této části se nachází v [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0Exp\Projects].  
  
 První identifikátor GUID je CLSID pro projekty tohoto typu; druhý identifikátor GUID označuje typ registrovaných projektu pro šablony přidat položky.  
  
 \\\1 \AddItemTemplates\TemplateDirs\ {ACEF4EB2-57CF-11D2-96F4-000000000000} {C061DB26-5833-11D2-96F5-000000000000}  
  
 @="#6"  
  
 "TemplatesDir"="\<cesta instalace Visual Studio SDK\\\VSIntegration\\\SomeFolder\\\SomePackage\\\SomeProject\\\SomeProjectItems"  
  
 "SortPriority" = dword:00000064  
  
|Název|Typ|Data (ze souboru .rgs)|Popis|  
|----------|----------|-----------------------------|-----------------|  
|@ (Výchozí)|REG_SZ|#% IDS_ADDITEM_TEMPLATES_ENTRY %|ID prostředku pro **přidat položku** šablony.|  
|Val TemplatesDir|REG_SZ|%TEMPLATE_PATH%\ SomeProjectItems|Cesta položky projektu zobrazí v dialogovém okně pro **přidat novou položku** průvodce.|  
|Val SortPriority|REG_DWORD|100 ([!INCLUDE[vcprx64](../../extensibility/internals/includes/vcprx64_md.md)])|Určuje pořadí řazení v uzlu stromu souborů v zobrazí **přidat novou položku** dialogové okno.|  
  
> [!NOTE]
>  Identifikátory GUID pro typy projektů Visual C# a Visual Basic jsou následující:[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]: {FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]: {F184B08F-C81C-45F6-A57F-5ABD9991F28F}  
  
 Adresář uvedené TemplateDirs, což je % TEMPLATE_PATH%\SomeProjectItems, je uzel na levé straně **přidat novou položku** dialogové okno pole stromu. Další prvky ve stromové struktuře jsou založené na podadresáře v tomto kořenový adresář. Položky v pravém podokně jsou k dispozici pro přidání do projektu soubory **přidat novou položku** dialogové okno.  
  
 Tato složka bude obvykle obsahovat soubory šablon pro svůj projekt jako šablonu HTML nebo souboru a všechny soubory pro spuštění průvodce. Pokud chcete řídit, jak jsou zobrazeny položky, můžete použít také .vsdir soubory pro lokalizace názvy adresářů a ikony. Lokalizovaný řetězec je popisek, který se zobrazí v dialogu, který představuje tento uzel ve stromu dialogové okno Přidat novou položku.  
  
 Však není nutné mít všechno, co v jedné projektový soubor. Může mít jeden projektový soubor pro každou položku v adresáři. Další informace najdete v tématu [průvodce (. Soubor vsz)](../../extensibility/internals/wizard-dot-vsz-file.md) a [Directory popis šablony (. Soubory VSDIR)](../../extensibility/internals/template-directory-description-dot-vsdir-files.md).  
  
> [!NOTE]
>  .Vsdir soubory v adresáři šablony jsou volitelné. Pokud chcete blokovat prvek projektu v adresáři a zobrazit ji v **přidat novou položku** dialogové okno, můžete vložit tento soubor v adresáři šablony zadaných v příkazu TemplatesDir. Soubor se pak zobrazí v pravém podokně **přidat novou položku** dialogové okno pro tento projekt. Pokud chcete zobrazit lokalizované titulek pro soubor nebo ikonu, můžete v adresáři šablony musí obsahovat alespoň jeden projektový soubor.  
  
## <a name="grouping-project-items"></a>Seskupení položek projektu  
 Pokud chcete obsahují skupiny šablony ve složkách v **přidat novou položku** dialogové okno pole stromu podadresáře v kořenovém adresáři šablony s položkami musí mít v nich. Když **přidat novou položku** dialogové okno se zobrazí uživatelům, budou také zobrazit podadresáře a bude moci vybrat z těchto prvků projektu.  
  
 Priorita řazení v segmentu kódu určuje, kde bude tento adresář šablony vytvořen ve stromové struktuře relativně k další prvky uzlu stromu. Pro **přidat novou položku** dialogové okno, prioritu řazení je všechno, která musí zahrnovat tak, aby vaše položky se zobrazí ve správném umístění v dialogovém okně.  
  
 Můžete taky implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> rozhraní pro filtrování, co se zobrazí v **přidat novou položku** dialogové okno. Implementací toto rozhraní nastavením jedna šablona adresáře na disku, který obsahuje, například 50 souborů průvodce a šablony. Tento způsob může mít různé typy projektů s 20 souborů, které patří do typy projektu, 30 souborů, které patří na jiný typ projektu a všechny soubory, které jsou k dispozici v obecné typu projektu. Tímto způsobem, v závislosti na tom, které projektu šablona vytvořena, můžete zobrazit jinou sadu soubory šablon.  
  
 V projektu jazyka Visual Basic, můžete například mít webové projekty a klientského projektu. Webové formuláře nejsou užitečné položek, které chcete přidat do projektu klienta a windows forms nejsou užitečné položek, které chcete přidat do projektu webového serveru. Proto můžete vytvořit jeden adresář šablony, která obsahuje všechny soubory pro oba typy projektu. Potom implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>, můžete skrýt, položky, které by se neměly zobrazovat, v závislosti na typu projektu nebo nastavení projektu v projektu.  
  
## <a name="filtering-project-items"></a>Filtrování položek projektu  
 `IVsFilterAddProjectItemDlg2`poskytuje pro filtrování elementů ve stromu (levé podokno) a soubory projektu (pravé podokno) následujícím způsobem:  
  
-   Lokalizované názvy (titulky zobrazí v dialogovém okně, které jsou obsaženy v projektový soubor), které poskytuje `IVsFilterAddProjectItemDlg`.  
  
-   Skutečné názvy souborů a složek na disku (Nelokalizováno – žádné projektový soubor) poskytované `IVsFilterAddProjectItemDlg`.  
  
-   Podle kategorií, poskytované `IVsFilterAddProjectItemDlg2`.  
  
 Chcete-li filtrovat podle kategorie, zadejte řetězec kategorie pro položky v projektový soubor, jako je například "Webového formuláře" nebo "Klienta položka" v jazyce Visual Basic. Pole kód tohoto dialogu potom načte kategorie klasifikace z projektový soubor a předává je na vás. Tyto informace můžete poté předat do vaší implementace nástroje `IVsFilterAddProjectItemDlg2` pro filtrování **přidat novou položku** dialogové okno podle kategorií. Můžete také filtrovat položky pro webové stránky nebo jako případech aplikace Win32 klienta. Kromě toho můžete identifikovat [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] označené položky jako Microsoft Foundation třídy (MFC) nebo aktivní šablony položek knihovny (ATL). Při určování tyto položky systému projektu můžete definovat vlastní klasifikace, aby systém je možné filtrovat podle kategorie a klasifikace.  
  
 Pokud implementujete tuto funkci filtru, nemáte mapovat tabulku každá položka, která má být skrytá. Jednoduše můžete klasifikovat položky do typy a klasifikace chápat projektový soubor nebo soubory. Potom můžete skrýt, některou z položek, které mají určité klasifikace implementací rozhraní. Tímto způsobem můžete provést položky v **přidat novou položku** dialogové okno pole dynamické na základě stavu v projektu.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)   
 [CATIDs pro objekty, které jsou obvykle používány k rozšíření projektů](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)   
 [Přidání projektů a šablon položek projektu](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [Popis Directory šablony (. Soubory VSDIR)](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)   
 [Průvodce (. Soubor vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)