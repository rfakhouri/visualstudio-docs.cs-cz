---
title: 'Postupy: Migrace jazyka specifického pro doménu na novou verzi | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 6a1ae073-443e-45ca-8bc9-9b944362b449
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7f3cefc7c6e2a78d757bb931a430f09c6da103c1
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65681049"
---
# <a name="how-to-migrate-a-domain-specific-language-to-a-new-version"></a>Postupy: Migrace jazyka specifického pro doménu na novou verzi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete migrovat projekty, které definice a používání jazyka specifického pro doménu na [!INCLUDE[vs2010](../includes/vs2010-md.md)] oproti verzi [!INCLUDE[dsl](../includes/dsl-md.md)] , který byl distribuován s [!INCLUDE[vs_orcas_long](../includes/vs-orcas-long-md.md)].  
  
 Nástroj pro migraci se poskytuje jako součást [!INCLUDE[vssdk_current_long](../includes/vssdk-current-long-md.md)]. Tento nástroj převede [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projekty a řešení, které používají nebo definovat nástroje DSL.  
  
 Nástroj pro migraci musíte spustit explicitně: se nespustí automaticky při otevření řešení v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Nástroje a dokument obsahuje podrobné pokyny najdete v této cestě:  
  
 **%Program Files%\Microsoft Visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**  
  
## <a name="before-you-migrate-your-dsl-projects"></a>Před migraci vašich projektů DSL  
 Nástroj pro migraci změní [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] soubory projektu (**.csproj**) a soubory řešení (**.sln**).  
  
#### <a name="to-prepare-projects-for-migration"></a>Příprava migrace projektů.  
  
- Ujistěte se, **.csproj** a **.sln** lze zapisovat soubory. Pokud jsou pod správou zdrojových kódů, ujistěte se, že jsou rezervovány.  
  
- Vytvořte kopii složky, které máte v úmyslu migrovat.  
  
## <a name="migrating-a-collection-of-projects"></a>Migrace kolekce projektů  
  
#### <a name="to-migrate-dsl-projects-and-solutions-to-visual-studio-2010"></a>K migraci DSL projekty a řešení pro Visual Studio 2010  
  
1. Spusťte nástroj pro migraci DSL.  
  
   - Můžete dvakrát klikněte na panel nástrojů v Průzkumníku Windows (nebo Průzkumníka souborů) nebo spusťte nástroj z příkazového řádku. Tento nástroj je v tomto umístění:  
  
        **%ProgramFiles%\Microsoft Visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**  
  
2. Zvolte složku, která obsahuje řešení a projekty, které chcete převést.  
  
   - Zadejte cestu do pole v horní části stránky nástroje, nebo klikněte na tlačítko **Procházet**.  
  
     Nástroj pro migraci zobrazí strom projektů, které definují nebo použijte DSL. Každý projekt, který používá zahrnuje stromu **Microsoft.VisualStudio.Modeling.Sdk** nebo **TextTemplating** sestavení.  
  
3. Kontrola stromu projektů a zrušte zaškrtnutí políčka projekty, které nechcete převést.  
  
   - Vyberte projekt nebo řešení zobrazíte seznam změn, které způsobí, že nástroj.  
  
       > [!NOTE]
       > Zaškrtávací políčka, které se zobrazují vedle názvu složky nemají žádný vliv. Je třeba rozbalit složky ke kontrole projekty a řešení.  
  
4. Převod projektů.  
  
   1. Klikněte na tlačítko **převést**.  
  
        Před každý soubor projektu je převést, kopie _projektu_**.csproj** budou uloženy jako _projektu_**. vs2008.csproj**  
  
        Kopírování jednotlivých _řešení_**.sln** budou uloženy jako _řešení_**. vs2008.sln**  
  
   2. Prozkoumejte všechny neúspěšné převody, které jsou hlášeny.  
  
        V textovém okně jsou hlášeny chyby. Kromě toho stromové zobrazení ukazuje rvená vlaječka v každém uzlu, který se nepovedlo převést. Můžete kliknout na uzel, který má získat další informace o této chybě.  
  
5. **Transformovat všechny šablony** v řešení obsahující úspěšně převeden projekty.  
  
   1. Otevřete řešení.  
  
   2. Klikněte na tlačítko **Transformovat všechny šablony** tlačítko v hlavičce Průzkumníku řešení.  
  
       > [!NOTE]
       > Tento krok můžete provést zbytečné. Další informace najdete v tématu [jak automatizovat Transformovat všechny šablony](https://msdn.microsoft.com/b63cfe20-fe5e-47cc-9506-59b29bca768a).  
  
6. Aktualizujte váš vlastní kód v projektech převedený.  
  
   - Pokus o sestavení projektů a prozkoumejte všechny chyby.  
  
   - Otestujte návrháře.  
  
## <a name="see-also"></a>Viz také  
 [Co je nového v produktu Visualization and Modeling SDK](../misc/what-s-new-in-visualization-and-modeling-sdk.md)
