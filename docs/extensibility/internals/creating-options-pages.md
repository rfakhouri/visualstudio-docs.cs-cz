---
title: "Vytváření stránek možnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed package framework, creating Tools Options pages
- Tools Options pages [Visual Studio SDK], creating using managed package framework
ms.assetid: 1bf11fec-dece-4943-8053-6de1483c43eb
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ae8540a2f372abacd8eda6e63cd868edbb050392
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="creating-options-pages"></a>Vytváření stránek možnosti
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] spravované balíček framework třídy odvozené od <xref:Microsoft.VisualStudio.Shell.DialogPage> rozšířit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE přidáním **možnosti** stránky v části **nástroje** nabídky.  
  
 Implementaci objektu danou **– možnost Nástroje** stránky je přidružen konkrétní VSPackages podle <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> objektu.  
  
 Protože prostředí vytvoří objekt implementující konkrétní **možnosti nástrojů** v případě, že danou stránku se zobrazí při integrovaného vývojového prostředí:  
  
-   A **– možnost Nástroje** stránka by měla být implementována na svůj vlastní objekt a ne na objekt implementující VSPackage.  
  
-   Objekt nelze implementovat, více **možnosti nástrojů** stránky.  
  
## <a name="registering-as-a-tools-options-page-provider"></a>Registrace jako poskytovatel nástroje Možnosti stránky  
 Konfiguraci VSPackage podpůrné uživatele prostřednictvím **možnosti nástrojů** stránky označuje objekty poskytuje tyto **možnosti nástrojů** stránky použitím instancí <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> použít <xref:Microsoft.VisualStudio.Shell.Package>implementace.  
  
 Musí být jedna instance <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> pro každý <xref:Microsoft.VisualStudio.Shell.DialogPage>-odvozený typ, který implementuje **možnosti nástrojů** stránky.  
  
 Každá instance <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> používá typ, který implementuje **možnosti nástrojů** stránky, řetězce, které obsahují kategorii a podkategorii použít k identifikaci **možnosti nástrojů** stránky a prostředků informace o registraci typu jako poskytování **možnosti nástrojů** stránky.  
  
## <a name="persisting-tools-options-page-state"></a>Zachování stavu stránky Možnosti nástroje  
 Pokud **možnosti nástrojů** stránky implementace je zaregistrován s povolenou podporou automatizaci, prostředí IDE přetrvává stav stránky stejně tak všechny další **možnosti nástrojů** stránky.  
  
 VSPackage můžete spravovat svůj vlastní trvalost pomocí <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute>. Třeba použít pouze jeden nebo jinou metodu trvalost.  
  
## <a name="implementing-dialogpage-class"></a>Implementace DialogPage – třída  
 Objekt poskytuje VSPackage na implementaci <xref:Microsoft.VisualStudio.Shell.DialogPage>-odvozený typ můžete využít výhod zděděné následující funkce:  
  
-   Okno výchozí uživatelské rozhraní.  
  
-   A výchozí mechanismus trvalosti dostupné buď pokud <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> se použije k třídě, nebo pokud <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute.SupportsProfiles%2A> je nastavena na `true` pro <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> který se použije k třídě.  
  
-   Podpora automatizace.  
  
 Minimální požadavky pro implementaci k objektu **možnosti nástrojů** stránky pomocí <xref:Microsoft.VisualStudio.Shell.DialogPage> je přidání veřejné vlastnosti.  
  
 Pokud třída řádně zaregistrován jako **možnosti nástrojů** stránky poskytovatele, pak jsou k dispozici na jeho veřejné vlastnosti **možnosti** části **nástroje** nabídky ve formě Vlastnost mřížky.  
  
 Všechny tyto funkce výchozí lze přepsat. Například vytvořte sofistikovanější uživatele rozhraní vyžaduje pouze přepsání výchozí implementaci <xref:Microsoft.VisualStudio.Shell.DialogPage.Window%2A>.  
  
## <a name="example"></a>Příklad  
 Co následuje je jednoduchý "text hello world" implementace stránku možnosti. Přidání následující kód do výchozího projektu vytvořený balíček šabloně Visual Studio se **příkaz nabídky** vybraná možnost bude demonstrovat adekvátní možnost stránky funkce.  
  
### <a name="description"></a>Popis  
 Následující třídy definuje minimální stránka Možnosti "hello world". Po otevření může uživatel nastavit veřejnosti `HelloWorld` vlastnost v tabulce vlastností.  
  
### <a name="code"></a>Kód  
 [!code-csharp[UI_UserSettings_ToolsOptionPages#11](../../extensibility/internals/codesnippet/CSharp/creating-options-pages_1.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#11](../../extensibility/internals/codesnippet/VisualBasic/creating-options-pages_1.vb)]  
  
### <a name="description"></a>Popis  
 Použití následující atribut k třídě balíček zpřístupní možnosti stránky při načtení balíčku. Čísla, která jsou libovolné ID prostředku pro kategorii a stránky a logickou hodnotu na konci Určuje, zda stránka podporuje automatizace.  
  
### <a name="code"></a>Kód  
 [!code-csharp[UI_UserSettings_ToolsOptionPages#07](../../extensibility/internals/codesnippet/CSharp/creating-options-pages_2.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#07](../../extensibility/internals/codesnippet/VisualBasic/creating-options-pages_2.vb)]  
  
### <a name="description"></a>Popis  
 Následující obslužné rutiny události zobrazí výsledku v závislosti na hodnotě vlastnost nastavená na stránce Možnosti. Použije <xref:Microsoft.VisualStudio.Shell.Package.GetDialogPage%2A> metoda s výsledkem explicitně přetypovat na typ stránky vlastní možnost pro přístup k vlastnostem vystavené stránky.  
  
 V případě projektu vygenerované šablony balíčku, volání této funkce z `MenuItemCallback` funkce připojit k příkazu výchozí přidán do **nástroje** nabídky.  
  
### <a name="code"></a>Kód  
 [!code-csharp[UI_UserSettings_ToolsOptionPages#08](../../extensibility/internals/codesnippet/CSharp/creating-options-pages_3.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#08](../../extensibility/internals/codesnippet/VisualBasic/creating-options-pages_3.vb)]  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření uživatelská nastavení a možnosti](../../extensibility/extending-user-settings-and-options.md)   
 [Podpora automatizace pro stránky Možnosti](../../extensibility/internals/automation-support-for-options-pages.md)