---
title: "Návod: Vytvoření služby jazyk starší | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- language services [managed package framework], creating
ms.assetid: 6a5dd2c2-261b-4efd-a3f4-8fb90b73dc82
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 660d33dd2d5c46d8020172c1fcf74bfb64b43360
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-legacy-language-service"></a>Návod: Vytvoření služby jazyk starší verze
Použití třídy jazyka framework (MPF) spravovaných balíček k implementaci služba jazyka v [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] je jednoduché. Je nutné VSPackage hostit služba jazyka, samotnou službu jazyk a analyzátor pro daný jazyk.  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li provést tento postup, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../../extensibility/visual-studio-sdk.md).  
  
## <a name="locations-for-the-visual-studio-package-project-template"></a>Umístění pro šablony sady Visual Studio balíčku projektu  
 Šabloně projektu sady Visual Studio balíčku naleznete ve třech umístěních jinou šablonu v **nový projekt** dialogové okno:  
  
1.  V části rozšiřitelnosti jazyka Visual Basic. Je výchozí jazyk projektu jazyka Visual Basic.  
  
2.  V části C# – rozšiřitelnost. Je výchozí jazyk projektu C#.  
  
3.  V části Další typy rozšiřitelnost projektů. Výchozí jazyk projektu je C++.  
  
### <a name="create-a-vspackage"></a>Vytvořit VSPackage  
  
1.  Vytvořte nový VSPackage pomocí šablony projektu balíček Visual Studio.  
  
     Pokud přidáváte služba jazyka do existující VSPackage, následující kroky přeskočte a přejděte přímo k postupu "Vytvoření the jazyk Service Class".  
  
2.  Zadejte MyLanguagePackage pro název projektu a klikněte na tlačítko **OK**.  
  
     Můžete použít jakýkoli název, který chcete. Tyto postupy popsané v tomto poli předpokládají MyLanguagePackage jako název.  
  
3.  Vyberte [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] jako jazyk a možnost k vygenerování nového klíče souboru. Klikněte na tlačítko **Další**.  
  
4.  Zadejte příslušné informace společnosti a balíčku. Klikněte na tlačítko **Další**.  
  
5.  Vyberte **příkaz nabídky**. Klikněte na tlačítko **Další**.  
  
     Pokud nemáte v úmyslu pro podporu fragmenty kódu, můžete jenom klikněte na tlačítko Dokončit a další krok ignorovat.  
  
6.  Zadejte **Vložit fragment** jako **příkaz název** a `cmdidInsertSnippet` pro **ID příkazu**. Klikněte na tlačítko **Dokončit**.  
  
     **Název příkazu** a **ID příkazu** lze libovolně, jenom příklady.  
  
### <a name="create-the-language-service-class"></a>Vytvořte třídu služba jazyka  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt MyLanguagePackage, zvolte **přidat**, **odkaz**a potom vyberte **přidat nový odkaz** tlačítko.  
  
2.  V **přidat odkaz na** dialogové okno, vyberte **Microsoft.VisualStudio.Package.LanguageService** v **.NET** a klikněte na **OK**.  
  
     To je potřeba udělat jenom jednou pro projekt jazyka balíčku.  
  
3.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt VSPackage a vyberte **přidat**, **třída**.  
  
4.  Zajistěte, aby **třída** je vybrán v seznamu šablon.  
  
5.  Zadejte **MyLanguageService.cs** pro název souboru třídy a klikněte na tlačítko **přidat**.  
  
     Můžete použít jakýkoli název, který chcete. Tyto postupy popsané v tomto poli předpokládá `MyLanguageService` jako název.  
  
6.  V souboru MyLanguageService.cs, přidejte následující `using` příkazy.  
  
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#1](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_1.cs)]
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#1](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_1.vb)]  
  
7.  Změnit `MyLanguageService` odvozena od třídy <xref:Microsoft.VisualStudio.Package.LanguageService> třídy:  
  
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#2](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_2.cs)]
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#2](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_2.vb)]  
  
8.  Umístěte kurzor na "LanguageService" a z **upravit**, **IntelliSense** nabídce vyberte možnost **abstraktní třída implementace**. Tento postup přidá minimální potřebné metody k implementaci třídu služby jazyk.  
  
9. Implementujte abstraktní metody, jak je popsáno v [implementace služby jazyk starší](../../extensibility/internals/implementing-a-legacy-language-service2.md).  
  
### <a name="register-the-language-service"></a>Registrovat službu jazyka  
  
1.  Otevřete soubor MyLanguagePackagePackage.cs a přidejte následující `using` příkazy:  
  
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#3](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_3.vb)]
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#3](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_3.cs)]  
  
2.  Registrovat třídu služby váš jazyk, jak je popsáno v [registrace služby jazyk starší](../../extensibility/internals/registering-a-legacy-language-service1.md). To zahrnuje atributy ProvideXX a části "Proffering služba jazyka Service". Použijte MyLanguageService, kde toto téma používá TestLanguageService.  
  
### <a name="the-parser-and-scanner"></a>Analyzátor a skener  
  
1.  Implementace analyzátor a skener pro váš jazyk, jak je popsáno v [analyzátoru služby starší verze jazyka a skener](../../extensibility/internals/legacy-language-service-parser-and-scanner.md).  
  
     Jak implementovat analyzátor a skener je zcela na vás a je nad rámec tohoto tématu.  
  
## <a name="language-service-features"></a>Funkce jazyka služby  
 K implementaci jednotlivých funkcí ve službě jazyk, je obvykle odvození třídy z třídě služby příslušné jazykové sady MPF, implementovat žádné abstraktní metody podle potřeby a přepsat příslušné metody. Jaké třídy Vytvoření nebo odvozena od je závisí na funkcích chcete podporovat. Tyto funkce jsou podrobněji v [starší verze funkce služby jazyk](../../extensibility/internals/legacy-language-service-features1.md). Následující postup je obecný přístup k odvození třídy z tříd sady MPF.  
  
#### <a name="deriving-from-an-mpf-class"></a>Odvozování z třídy sady MPF  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt VSPackage a vyberte **přidat**, **třída**.  
  
2.  Zajistěte, aby **třída** je vybrán v seznamu šablon.  
  
     Zadejte požadovaný název souboru třídu a klikněte na tlačítko **přidat**.  
  
3.  V souboru nové třídy, přidejte následující `using` příkazy.  
  
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#4](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_4.cs)]
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#4](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_4.vb)]  
  
4.  Upravte třídy odvozovat ze sady MPF požadovanou třídu.  
  
5.  Přidejte konstruktor – třída, která přebírá alespoň stejné parametry jako základní třída – konstruktor a předat parametry konstruktor k konstruktor základní třídy.  
  
     Například v konstruktoru třídy odvozené od <xref:Microsoft.VisualStudio.Package.Source> třída může vypadat třeba takto:  
  
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#5](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_5.cs)]
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#5](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_5.vb)]  
  
6.  Z **upravit**, **IntelliSense** nabídce vyberte možnost **abstraktní třída implementace** Pokud základní třída má všechny abstraktní metody, které musí být implementována.  
  
7.  Jinak hodnota pozice vsuvka uvnitř třídy a zadejte metodu k přepsání.  
  
     Můžete například zadat `public override` zobrazte seznam všech metod, které mohou být přepsána nastaveními v třídy.  
  
## <a name="see-also"></a>Viz také  
 [Implementace služby jazyk starší verze](../../extensibility/internals/implementing-a-legacy-language-service1.md)