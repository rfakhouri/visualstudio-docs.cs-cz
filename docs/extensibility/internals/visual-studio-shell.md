---
title: Prostředí sady Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- shell, Visual Studio
- Visual Studio, shell
ms.assetid: cb124ef4-1a6b-4bfe-bfbf-295ef9c07f36
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 71b624cee0e55f95f90a86eac943828bbc26ac97
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31144353"
---
# <a name="visual-studio-shell"></a>Visual Studio Shell
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Prostředí je primární agenta integrace v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Prostředí poskytuje nezbytné funkce umožňující VSPackages sdílení společných služeb. Protože architektury cílem [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je vzor průmyslovému primární funkce VSPackages, prostředí je rozhraní k poskytování základních funkcí a podporovat komunikaci mezi mezi jeho součásti VSPackages.  
  
## <a name="shell-responsibilities"></a>Odpovědnosti prostředí  
 Prostředí má následující klíče zodpovědnosti:  
  
-   Podpora (prostřednictvím rozhraní modelu COM) základní prvky uživatelského rozhraní (UI). Patří sem výchozí nabídek a panelů nástrojů, rámce okna dokumentu nebo podřízená okna rozhraní více dokumentů (MDI) a rámce okna nástrojů a ukotvení podpory.  
  
-   Aby bylo možné koordinovat trvalost dokumentů a zaručit, že jeden dokument nelze otevřít, více než jedním způsobem, nebo nekompatibilní způsoby za údržbu spuštěné seznam všechny aktuálně otevřené dokumenty ve spuštěné tabulce dokumentu (r...).  
  
-   Podpora rozhraní směrování příkazů a příkaz zpracování `IOleCommandTarget`.  
  
-   Načítání VSPackages v příslušnou dobu. Načtení zpoždění VSPackage je nezbytné pro zlepšení výkonu prostředí.  
  
-   Správa určité sdílených služeb, jako například <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>, která poskytuje funkce základní prostředí, a <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>, která poskytuje základní oddílová funkce.  
  
-   Správa souborů řešení (.sln). Řešení obsahují skupiny související projekty, podobně jako do pracovního prostoru (.dsw) souborů Visual C++ verze 6.0.  
  
-   Výběr sledování celé prostředí, kontextu a měny. Prostředí sleduje následující typy položek:  
  
    -   V aktuálním projektu  
  
    -   Aktuální položka projektu nebo ItemID aktuální <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>  
  
    -   Aktuální výběr **vlastnosti** okno nebo `SelectionContainer`  
  
    -   Kontext uživatelského rozhraní ID nebo CmdUIGuids, která řídí viditelnost příkazy, nabídek a panelů nástrojů  
  
    -   Aktuálně aktivní prvky, jako jsou například aktivní okno, dokument a manager vrácení zpět  
  
    -   Atributy kontextu uživatele, které jednotka dynamické nápovědy  
  
 Prostředí také zprostředkovává komunikaci mezi nainstalovaných VSPackages a aktuální služby. Podporuje základní funkce prostředí a dává je k dispozici všechny VSPackages integrovaná [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Tyto základní funkce zahrnují následující položky:  
  
-   **O** dialogové okno pole a úvodní obrazovky  
  
-   **Přidat nové a přidat existující položku** dialogových oken  
  
-   **Třídy zobrazení** okno a **Prohlížeč objektů**  
  
-   **Odkazy na** dialogové okno  
  
-   **Osnova dokumentu** okna  
  
-   **Dynamické nápovědy** okna  
  
-   **Najít** a **nahradit**  
  
-   **Otevřete projekt** a **otevření souboru** dialogových oknech na **nový** nabídky  
  
-   **Možnosti** dialogové okno na **nástroje** nabídky  
  
-   **Vlastnosti** okna  
  
-   **Průzkumník řešení**  
  
-   **Seznam úkolů** okna  
  
-   **Panel nástrojů**  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>   
 [Balíčky VSPackage](../../extensibility/internals/vspackages.md)