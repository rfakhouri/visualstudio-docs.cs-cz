---
title: "Cílení na více verzí sady Visual Studio – přehled | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- targeting .NET Framework version [Visual Studio]
- versions [Visual Studio], targeting .NET Framework version
- multi-targeting [Visual Studio]
- multitargeting [Visual Studio]
ms.assetid: b1702c33-0672-4ebc-b779-2b324d6ea880
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ad2917a1cf0a620f2e228828a152d91ec8948734
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-multi-targeting-overview"></a>Přehled cílení na více verzí sady Visual Studio
V této verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], můžete zadat verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] , který je vyžadován pro vaši aplikaci. Proto pokud chcete použít tuto verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] k dál vyvíjet projekt, který jste spustili ve starší verzi, nemáte změnit cílový framework. Můžete také vytvořit řešení, které obsahují projekty tento cíl různé verze rozhraní. Cílení na Framework také pomáhá zaručit, že aplikace bude používat jenom funkce, které jsou k dispozici v zadaná verze rozhraní.  
  
> [!TIP]
>  Také můžete určit cílovou aplikací pro různé platformy. Další informace najdete v tématu [cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md)  
  
## <a name="framework-targeting-features"></a>Funkce cílení Framework  
 Cílení na Framework zahrnuje následující funkce:  
  
-   Při otevření projektu, jehož cílem dřívější verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] lze automaticky upgradovat nebo nechte cíl, jako je.  
  
-   Když vytvoříte projekt, můžete zadat verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] , kterou chcete cílit.  
  
-   Můžete změnit verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] existující projekt, cílem.  
  
-   Můžete vybrat jinou verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] v každé z několika projektů ve stejném řešení.  
  
-   Když změníte verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] který cíle projektu, [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] provede požadované změny odkazů a konfigurační soubory.  
  
 Pokud pracujete na projektu, jehož cílem dřívější verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], Visual Studio dynamicky změní vývojového prostředí, následujícím způsobem:  
  
-   Filtruje položky v **nový projekt** dialogové okno, **přidat novou položku** dialogové okno, **přidat nový odkaz** dialogové okno a **přidat odkaz na službu** dialogové okno Možnosti, které nejsou k dispozici v cílové verzi vynechat.  
  
-   Filtruje vlastní ovládací prvky v **sada nástrojů** odeberte ty, které nejsou k dispozici v cílové verzi a zobrazit pouze nejnovější ovládacích prvků, když jsou k dispozici více ovládacích prvků.  
  
-   Filtruje technologii IntelliSense, která vynechejte jazykové funkce, které nejsou k dispozici v cílové verzi.  
  
-   Filtruje vlastnosti v **vlastnosti** okno na ty, které nejsou k dispozici v cílové verzi vynechejte.  
  
-   Filtruje možností v nabídce Možnosti, které nejsou k dispozici v cílové verzi vynechat.  
  
-   Pro sestavení používá verzi kompilátor a možnosti kompilátoru, které jsou vhodné pro cílovou verzi.  
  
> [!NOTE]
>  Cílení na Framework nezaručuje, bude vaše aplikace správně spuštěn. Vaše aplikace a ujistěte se, že je spuštěna s cílovou verzi, musíte otestovat. Cílem nemůže framework verze starší než rozhraní .NET Framework 2.0.  
  
## <a name="selecting-a-target-framework-version"></a>Výběr cílové verze Framework  
 Když vytvoříte projekt, vyberte cíl [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verzi v **nový projekt** dialogové okno. V seznamu šablon projektu k dispozici je filtrovaná podle výběru. V existujícího projektu, můžete změnit cíl [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verzi v dialogovém okně Vlastnosti projektu. Další informace najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
> [!NOTE]
>  V edicích sady Visual Studio Express nelze nastavit cílovém Frameworku, který **nový projekt** dialogové okno.  
  
## <a name="resolving-system-and-user-assembly-references"></a>Řešení systém a odkazy na sestavení uživatele  
 Chcete-li cílové verze rozhraní .NET Framework, musíte nejprve nainstalovat odkazy na příslušné sestavení. Odkazy na sestavení pro rozhraní .NET Framework verze 2.0, 3.0 a 3.5 jsou zahrnuty v rozhraní .NET Framework 3.5 SP1, kterou si můžete stáhnout z [Microsoft Download Center, Microsoft Visual Studio](http://go.microsoft.com/fwlink/?LinkId=227602) webu. Odkazy na sestavení pro profil klienta rozhraní .NET Framework 3.5, .NET Framework 4, .NET Framework 4 Client Profile a Silverlight jsou dostupné i z [Visual Studio stáhne](http://go.microsoft.com/fwlink/?LinkId=179687) webu.  
  
> [!NOTE]
>  Profil klienta rozhraní .NET Framework je podmnožinu rozhraní .NET Framework, která poskytuje omezenou sadu funkcí a knihovny. Další informace o profilech klienta najdete v tématu [profil klienta rozhraní .NET Framework](/dotnet/framework/deployment/client-profile).  
  
 **Přidat odkaz na** dialogové okno zakáže sestavení systému, které se netýkají cíl [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verze tak, že není možné je přidat do projektu nechtěně. (Systém sestavení jsou soubory .dll, které jsou součástí [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verzi.) Odkazy, které patří do framework verzi, která je novější než verze cílové nevyřeší a ovládací prvky, které jsou závislé na takový odkaz nelze přidat. Pokud chcete povolit odkazu, obnovit [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] cíl, které obsahuje odkaz na projekt.  Další informace najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
 Další informace o odkazy na sestavení najdete v tématu [řešení sestavení v době návrhu](../msbuild/resolving-assemblies-at-design-time.md).  
  
## <a name="enabling-linq"></a>Povolení LINQ  
 Když cílové rozhraní .NET Framework 3.5 nebo novější, odkaz na System.Core a import úrovni projektu pro System.Linq (v pouze v jazyce Visual Basic), se přidávají automaticky. Pokud chcete používat funkce LINQ, musíte také zapnout Option Infer (v pouze v jazyce Visual Basic). Referenční dokumentace a import se automaticky odeberou, když si změnit cíl na starší verzi rozhraní .NET Framework. Další informace najdete v tématu [práce s dotazy LINQ](/dotnet/csharp/tutorials/working-with-linq).  
  
## <a name="see-also"></a>Viz také  
 [Cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md)   
 [Kompatibilita a systémové požadavky na platformu](http://www.microsoft.com/visualstudio/eng/products/compatibility)