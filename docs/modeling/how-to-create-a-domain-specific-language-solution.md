---
title: "Postupy: vytvoření řešení jazyka domény | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.designerwizard
helpviewer_keywords:
- Domain-Specific Language Tools, walkthroughs
- walkthroughs [Domain-Specific Language Tools], creating domain-specific language
- Domain-Specific Language Tools, creating solutions
ms.assetid: e585b63b-34d2-405a-8d81-39ea22317975
caps.latest.revision: "41"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: b7c6f6f854e17e9b3b19f277d49674c311edb41b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-create-a-domain-specific-language-solution"></a>Postupy: Vytváření řešení jazyka specifického pro doménu
Jazyk specifické pro doménu (DSL) je vytvořená pomocí specializované [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení.  
  
## <a name="prerequisites"></a>Požadavky  
 Před zahájením tohoto postupu, je třeba nejprve nainstalovat tyto komponenty:  
  
|||  
|-|-|  
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkID=185579)|  
|[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkID=185580)|  
|Visual Studio vizualizace a modelování SDK||  


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

  
## <a name="creating-a-domain-specific-language-solution"></a>Vytváření řešení jazyka domény  
  
#### <a name="to-create-a-domain-specific-language-solution"></a>Chcete-li vytvořit řešení jazyka domény  
  
1.  Spustíte Průvodce DSL.  
  
    1.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
    2.  **Nový projekt** zobrazí se dialogové okno.  
  
    3.  V části **typy projektů**, rozbalte **jiné typy projektů** uzel a klikněte na tlačítko **rozšiřitelnost**.  
  
    4.  Klikněte na tlačítko **Návrhář jazyka domény**.  
  
    5.  V **název** zadejte název pro řešení. Click **OK**.  
  
         **Specifické pro doménu jazyk Návrhář průvodce** se zobrazí.  
  
        > [!NOTE]
        >  Název, který zadáte ideálně by měl být platný Visual C# identifikátor, protože může být použit pro generování kódu.  
  
     ![Dialogové okno DSL vytvořit](../modeling/media/create_dsldialog.png "Create_DSLDialog")  
  
2.  Vyberte šablonu DSL.  
  
     Na **vyberte specifické pro doménu jazykového** vyberte jednu z šablon řešení, jako **minimální jazyk**. Vyberte šablonu, která je podobná DSL, který chcete vytvořit.  
  
     Další informace o šablonách řešení najdete v tématu [výběr šablony řešení jazyk specifické pro doménu](../modeling/choosing-a-domain-specific-language-solution-template.md).  
  
3.  Zadejte příponu názvu souboru na **příponu souboru** stránky. Musí být jedinečný. v počítači a ve všech počítačů, ve kterých chcete instalovat DSL. Měli byste vidět zprávu **žádné aplikace ani Visual Studio editory použít tuto příponu**.  
  
    -   Pokud příponu názvu souboru jste použili v předchozí experimentální DSL, linky které plně nenainstalovali, můžete zrušit jejich odhlašování pomocí **resetovat experimentální instanci** nástroj, který lze nalézt v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] SDK nabídky.  
  
    -   Pokud jiný [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření, která používá tuto příponu souboru je plně nainstalován v počítači, zvažte jeho odinstalování. Na **nástroje** nabídky, klikněte na tlačítko **Správce rozšíření**.  
  
4.  Zkontrolujte a v případě potřeby upravit, polí v dalších stránkách průvodce. Jakmile budete spokojeni s nastavením, klikněte na tlačítko **Dokončit**. Další informace o nastaveních najdete v tématu [stránky průvodce Návrhář DSL](#settings).  
  
     Průvodce vytvoří řešení, která má dva projekty, které jsou s názvem **Dsl** a **DslPackage**.  
  
    > [!NOTE]
    >  Pokud se zobrazí zpráva, která vás upozorní, není ke spuštění textové šablony z nedůvěryhodných zdrojů, klikněte na tlačítko **OK**. Tato zpráva se zobrazí znovu, můžete nastavit.  
  
##  <a name="settings"></a>Stránky průvodce návrháře DSL  
 Můžete ponechat několik polí beze změny z výchozí hodnoty. Ale ujistěte se, nastavit pole příponu souboru.  
  
### <a name="solution-settings-page"></a>Stránka nastavení řešení  
 **Šablonu, kterou chcete založit na vaše konkrétní jazyk domény?**  
 Vyberte šablonu, která je podobná DSL, který chcete vytvořit. Různé šablony poskytují pohodlný počáteční body. Když vyberete šablonu řešení, Průvodce zobrazí popis. Další informace o šablonách řešení najdete v tématu [výběr šablony řešení jazyk specifické pro doménu](../modeling/choosing-a-domain-specific-language-solution-template.md).  
  
 **Zadejte název vaší domény jazyka?**  
 Výchozí hodnota je název řešení. Kód se vygeneroval ze tuto hodnotu. Musí být platný název třídy jazyka C#.  
  
### <a name="file-extension-page"></a>Stránka příponu souboru  
 **Jaká rozšíření by měl model soubory použít?**  
 Zadejte novou příponu souboru.  
  
 Ověřte, že tuto příponu souboru již zaregistrován pro použití v tomto počítači následujícím způsobem:  
  
 Podívejte se do části **další nástroje a aplikace pro zpracování toto rozšíření registrována**. Pokud se zobrazí zpráva **žádné aplikace ani Visual Studio editory použít tuto příponu**, můžete použít tuto příponu souboru.  
  
 Pokud se zobrazí seznam nástrojů nebo balíčky, proveďte jednu z těchto možností:  
  
-   Zadejte jinou příponu souboru.  
  
     \-nebo –  
  
-   Obnovit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] experimentální instanci. Zruší registraci všechny DSL, které jste dříve vytvořili linky. Na **spustit** nabídky, klikněte na tlačítko **všechny programy**, **Microsoft Visual Studio 2010 SDK**, **nástroje**a potom **resetovat Microsoft Visual Studio 2010 experimentální instanci**. Umožňuje obnovit všechny ostatní DSL, linky, který chcete znovu použít.  
  
     \-nebo –  
  
-   Pokud [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření, která používá tuto příponu souboru je plně nainstalován v počítači, odinstalujte ji. Na **nástroje** nabídky, klikněte na tlačítko **Správce rozšíření**.  
  
### <a name="product-settings-page"></a>Stránka nastavení produktu  
 **Jaký je název produktu, který patří nový jazyk specifické pro doménu?**  
 Výchozí hodnota je název DSL.  
  
 Tato hodnota se používá v Průzkumníku Windows (nebo Průzkumníka souborů) k popisu soubory, které mají tuto příponu souboru.  
  
 **Co je na název společnosti, který je součástí produktu?**  
 Název vaší společnosti.  
  
 Tato hodnota je součástí vlastností AssemblyInfo vašeho DSL balíčku.  
  
 **Co je kořenový obor názvů pro projekty v řešení?**  
 Tato výchozí název skládá z vaší společnosti a názvy produktů.  
  
### <a name="signing-page"></a>stránka Podepisování  
 **Vytvořte soubor klíče se silným názvem**  
 Výchozí možností je vytvořit nový klíč k podepsání vašeho DSL sestavení.  
  
 **Použít existující klíč silným názvem**  
 Tuto možnost použijte, pokud chcete integrovat váš DSL jiné sestavení.  
  
 Další informace o silné názvy najdete v tématu [vytvoření a použití sestavení](http://go.microsoft.com/fwlink/?LinkId=186073).  
  
## <a name="see-also"></a>Viz také  
 [Jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md)   
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)
