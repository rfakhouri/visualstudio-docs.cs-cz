---
title: "Podpora pro navigační panel ve službě jazyk starší | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Navigation bar, supporting in language services [managed package framework]
- language services [managed package framework], Navigation bar
ms.assetid: 2d301ee6-4523-4b82-aedb-be43f352978e
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5e2d7ddfd4904923cbdea415fa5a0d2086cc071f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="support-for-the-navigation-bar-in-a-legacy-language-service"></a>Podpora pro navigační panel ve službě jazyk starší verze
Navigační panel v horní části editoru zobrazení zobrazí typy a členy v souboru. V levém rozevíracího seznamu jsou uvedeny typy a členy se zobrazují v pravém rozevíracího seznamu. Když uživatel vybere typ, pomocí kurzoru je umístěn na prvním řádku typu. Když uživatel vybere člena, pomocí kurzoru je umístěn na definici tohoto člena. Rozevírací seznamy jsou aktualizovány tak, aby odrážela aktuální umístění pomocí kurzoru.  
  
## <a name="displaying-and-updating-the-navigation-bar"></a>Zobrazení a aktualizace navigačního panelu  
 Pro podporu navigačním panelu, musíte odvození třídy z <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> třídy a implementovat <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> metoda. Pokud vaše služba jazyka je zadána okno kódu, základní <xref:Microsoft.VisualStudio.Package.LanguageService> vytvoří instanci třídy <xref:Microsoft.VisualStudio.Package.CodeWindowManager>, obsahující <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> objekt reprezentující okno kódu. <xref:Microsoft.VisualStudio.Package.CodeWindowManager> Objekt potom bude mít nový <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> objektu. <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A> Metoda získá <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> objektu. Pokud vrátit instanci třídy vaše <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> třídy, <xref:Microsoft.VisualStudio.Package.CodeWindowManager> volání vaše <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> metoda k naplnění interní uvádí a předá vaše <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> do objektu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] rozevíracího seznamu panelu správce. Z rozevírací nabídky panelu Správce, pak zavolá <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.SetDropdownBar%2A> metoda na vaše <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> objekt, který chcete vytvořit <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBar> objekt, který obsahuje dva řádky rozevíracího seznamu.  
  
 Pokud se přesune pomocí kurzoru, <xref:Microsoft.VisualStudio.Package.LanguageService.OnIdle%2A> volání metod <xref:Microsoft.VisualStudio.Package.LanguageService.OnCaretMoved%2A> metoda. Základní <xref:Microsoft.VisualStudio.Package.LanguageService.OnCaretMoved%2A> volání metod <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> metoda ve vaší <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> třída k aktualizaci stavu na navigačním panelu. Předat sadu <xref:Microsoft.VisualStudio.Package.DropDownMember> objekty, které se tato metoda. Každý objekt představuje položku v rozevíracím seznamu.  
  
## <a name="the-contents-of-the-navigation-bar"></a>Obsah navigačního panelu  
 Navigační panel obvykle obsahuje seznam typů a seznam členů. Seznam typů obsahuje všechny typy, které jsou k dispozici v aktuální zdrojový soubor. Názvy typů obsahovat informace o dokončení oboru názvů. Následuje příklad kódu C# s dva typy:  
  
```csharp  
namespace TestLanguagePackage  
{  
    public class TestLanguageService  
    {  
        internal struct Token  
        {  
            int tokenID;  
        }  
        private Tokens[] tokens;  
        private string serviceName;  
    }  
}  
```  
  
 Zobrazí seznam typů `TestLanguagePackage.TestLanguageService` a `TestLanguagePackage.TestLanguageService.Tokens`.  
  
 Zobrazí se seznam členů Dostupní členové typu, který je vybraný v seznamu typů. Pomocí výše uvedeného příkladu kódu, pokud `TestLanguagePackage.TestLanguageService` je typ, který je vybraný seznam členů by obsahovat soukromé členy `tokens` a `serviceName`. Interní `Token` se nezobrazí.  
  
 Seznam členů tučným písmem název člena pomocí kurzoru při umístění uvnitř ho můžete implementovat. Členy můžete také zobrazí v šedě text, která určuje, že nejsou v rámci oboru, kde je aktuálně nastavený pomocí kurzoru.  
  
## <a name="enabling-support-for-the-navigation-bar"></a>Povolení podpory pro navigační panel  
 Chcete-li povolit podporu pro navigační panel, musíte nastavit `ShowDropdownBarOption` parametr <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> atribut `true`. Tento parametr nastavuje <xref:Microsoft.VisualStudio.Package.LanguagePreferences.ShowNavigationBar%2A> vlastnost. Pro podporu navigačním panelu, je nutné implementovat <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> objekt v <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A> metoda na <xref:Microsoft.VisualStudio.Package.LanguageService> třídy.  
  
 V implementaci <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A> metoda, pokud <xref:Microsoft.VisualStudio.Package.LanguagePreferences.ShowNavigationBar%2A> je nastavena na `true`, můžete se vrátit <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> objekt. Pokud není vrátí objekt, se nezobrazí na navigačním panelu.  
  
 Možnost zobrazit navigační panel lze nastavit uživatelem, takže je možné pro tento ovládací prvek resetování editor zobrazení je otevřen. Uživatel musí zavřete a znovu otevřete okno editoru před uplatněním změny.  
  
## <a name="implementing-support-for-the-navigation-bar"></a>Implementace podporu pro navigační panel  
 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> Metoda přebírá dva seznamy (jeden pro každou rozevíracího seznamu) a dvě hodnoty představující aktuální výběr v každém seznamu. Seznamy a výběr hodnoty mohou být aktualizovány, v takovém případě <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> metoda musí vrátit `true` indikující, že došlo ke změně seznamy.  
  
 Výběr změn v typech rozevíracího seznamu ve seznamu členů musí aktualizovat tak, aby odrážela nového typu. Co se zobrazí v seznamu členů, může být buď:  
  
-   Seznam členů pro aktuální typ.  
  
-   Všechny členy k dispozici ve zdroji souborů, ale s všichni členové není v aktuálním typem zobrazí šedě text. Uživatele můžete vybrat členy zašedlá, mohou být použity pro rychlé navigační, ale barvu označuje, že nejsou součástí aktuálně vybraného typu.  
  
 Implementace <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> metoda obvykle provede následující kroky:  
  
1.  Získejte seznam aktuální deklarace pro zdrojový soubor.  
  
     Existuje několik způsobů, jak naplnit seznamy. Jeden z přístupů je vytvořit vlastní metodu na vaší verzi <xref:Microsoft.VisualStudio.Package.LanguageService> třídu, která volá <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda s tímto důvodem vlastní analýzy, který vrátí seznam všech deklarací. Jiná možnost může být k volání <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda přímo z <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> metodu se z důvodu vlastní analýzy. Třetí přístup může být pro ukládání do mezipaměti deklarace v <xref:Microsoft.VisualStudio.Package.AuthoringScope> třída vrácená operací poslední úplné analýzy v <xref:Microsoft.VisualStudio.Package.LanguageService> třídy a načtení, která z <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> metoda.  
  
2.  Naplnění nebo aktualizujte seznam typů.  
  
     Seznam typů obsahu může aktualizovat, když došlo ke změně zdroji, nebo pokud jste se rozhodli změnit styl textu typů založené na aktuální pozici pomocí kurzoru. Všimněte si, že je předán této pozice <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> metoda.  
  
3.  Určuje typ a vyberte v seznamu typů založené na aktuální pozici pomocí kurzoru.  
  
     Můžete vyhledat deklarace, které byly získány v kroku 1 se najít typ, která obklopuje aktuální pozici pomocí kurzoru a pak v seznamu typů pro tento typ určit její index do seznamu typů Hledat.  
  
4.  Naplnění nebo aktualizovat seznam členů podle vybraného typu.  
  
     Seznam členů odráží, co je zobrazeno v **členy** rozevíracího seznamu. Obsah seznam členů možná muset aktualizovat, pokud došlo ke změně zdroji, nebo pokud jsou zobrazení pouze členové vybraného typu a se změnila vybraného typu. Pokud chcete zobrazit všechny členy v zdrojový soubor, pak styl textu u každého člena v seznamu je třeba aktualizovat, pokud došlo ke změně aktuálně vybraného typu.  
  
5.  Zjistěte člena vyberte v seznamu členů založené na aktuální pozici pomocí kurzoru.  
  
     Hledání deklarace, které byly získány v kroku 1 pro člena, který obsahuje aktuální pozici vsuvka a potom najděte seznam členů pro tento člen určit její index do seznamu členů.  
  
6.  Vrátí `true` Pokud byly provedeny změny seznamy nebo výběrů v seznamech.