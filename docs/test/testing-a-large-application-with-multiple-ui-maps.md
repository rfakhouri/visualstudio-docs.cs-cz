---
title: "Testování rozsáhlé aplikace s více mapami uživatelského rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- coded UI tests, multiple UI maps
- coded UI tests, for large applications
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: ca9114dfe601f523878749593a213b36465bd0a7
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="testing-a-large-application-with-multiple-ui-maps"></a>Testování rozsáhlé aplikace s více mapami uživatelského rozhraní
Toto téma popisuje postup použití programových testů uživatelského rozhraní při testování rozsáhlé aplikace s použitím více mapami uživatelského rozhraní.  
  
 **Požadavky**  
  
-   Visual Studio Enterprise  
  
 Při vytváření nového programového testu uživatelského rozhraní, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] testování framework generuje kód pro test ve výchozím nastavení <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> třídy. Další informace o tom, jak záznam programové testy uživatelského rozhraní, najdete v části [vytváření programových testů uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate) a [anatomie programového testu uživatelského rozhraní](../test/anatomy-of-a-coded-ui-test.md).  
  
 Generovaný kód pro mapu uživatelského rozhraní obsahuje třídu pro každý objekt, který komunikuje test. Pro každou metodu generované je doprovodný třídu pro parametry metody vygenerován speciálně pro dané metody. Pokud existuje velký počet objektů, stránky, formuláře a ovládací prvky v aplikaci, můžou růst velké mapy uživatelského rozhraní. Navíc několik lidí práci testy, aplikace se změní na nepraktické s jeden velký soubor mapy uživatelského rozhraní.  
  
 Použití více souborů mapy uživatelského rozhraní můžou poskytovat následující výhody:  
  
-   Každé mapování může být přidružen podmnožinu logické aplikace. To výrazně zjednodušuje změny ke správě.  
  
-   Každý tester můžete pracovat v oddílu aplikace a jejich kódu se změnami bez ovlivnění dalších testery práce v dalších částech aplikace.  
  
-   Přidání do aplikace uživatelského rozhraní je možné rozšířit přírůstkově s minimální vliv na testy pro dalších částí uživatelského rozhraní.  
  
## <a name="do-you-need-multiple-ui-maps"></a>Potřebujete více mapami uživatelského rozhraní?  
 Vytvořte více mapami uživatelského rozhraní v každém z těchto typů situacích:  
  
-   Několik komplexní sady složené ovládací prvky uživatelského rozhraní, které společně provádějí logické operace, jako je například registrační stránku na webu nebo stránce Nákup nákupního košíku.  
  
-   Ovládací prvky, které jsou přístupné z různých bodů aplikaci, například Průvodce s více stránkách operací sada nezávisle. Pokud je obzvláště složité jednotlivých stránkách průvodce, můžete vytvořit samostatné mapami uživatelského rozhraní pro jednotlivé stránky.  
  
## <a name="adding-multiple-ui-maps"></a>Přidání více mapami uživatelského rozhraní  
  
#### <a name="to-add-a-ui-map-to-your-coded-ui-test-project"></a>Chcete-li přidat mapu uživatelského rozhraní do projektu programových testů uživatelského rozhraní  
  
1.  V **Průzkumníku řešení**, abyste vytvořili složku v projektu programových testů uživatelského rozhraní pro uložení všech mapami uživatelského rozhraní, klikněte pravým tlačítkem na soubor projektu programového testu uživatelského rozhraní, přejděte na **přidat** a potom zvolte **novou složku**. Například mohla mít název `UIMaps`.  
  
     Do nové složky se zobrazí v části projektu programového testu uživatelského rozhraní.  
  
2.  Klikněte pravým tlačítkem myši `UIMaps` složku, přejděte na příkaz **přidat**a potom zvolte **novou položku**.  
  
     **Přidat novou položku** se zobrazí dialogové okno.  
  
    > [!NOTE]
    >  Musí být v programových projekt testů uživatelského rozhraní pro přidání nové mapování programových testů uživatelského rozhraní.  
  
3.  Vyberte **programového testu mapy uživatelského rozhraní** ze seznamu.  
  
     V **název** zadejte název nové mapování uživatelského rozhraní. Použijte název komponenty nebo stránky, která bude představovat mapy, například `HomePageMap`.  
  
4.  Zvolte **přidat**.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Minimalizuje okno a **Tvůrce programového testu uživatelského rozhraní** se zobrazí dialogové okno.  
  
5.  Záznam akcí pro první metodu a zvolte **generovat kód**.  
  
6.  Po zaznamenává všechny akce a kontrolní výrazy pro první součást nebo stránce a jejich seskupeny do metody, zavřete **Tvůrce programového testu uživatelského rozhraní** dialogové okno.  
  
7.  Pokračujte ve vytváření mapami uživatelského rozhraní. Záznam akcí a kontrolní výrazy, seskupovat je do metody pro jednotlivé součásti a poté generování kódu.  
  
 V mnoha případech okno nejvyšší úrovně vaší aplikace konstantní pro všechny průvodců, formuláře a stránky. I když každý mapy uživatelského rozhraní obsahuje třídu pro okno nejvyšší úrovně, jsou všechny mapy pravděpodobně odkazující na stejné okno nejvyšší úrovně v rámci které všechny součásti aplikace spustit. Programové uživatelského rozhraní testy hledá ovládací prvky hierarchicky shora dolů, počínaje z okna nejvyšší úrovně, komplexní aplikace, může být duplicitní okno skutečné nejvyšší úrovně v každé mapy uživatelského rozhraní. Pokud okno skutečné nejvyšší úrovně je duplicitní, provádění více úprav dojde, pokud toto okno změní. To může způsobit problémy s výkonem při přepínání mezi mapami uživatelského rozhraní.  
  
 Chcete-li minimalizovat tento efekt, můžete použít `CopyFrom()` metoda zajistit, aby nové okno nejvyšší úrovně, mapy uživatelského rozhraní jsou stejné jako hlavní okno nejvyšší úrovně.  
  
## <a name="example"></a>Příklad  
 Následující příklad je součástí nástroje třídu, která poskytuje přístup k jednotlivé komponenty a jejich podřízené ovládací prvky, které jsou reprezentované pomocí třídy vygenerované v různých mapami uživatelského rozhraní.  
  
 V tomto příkladu webovou aplikaci s názvem `Contoso` má domovskou stránku, na stránce produktu a na stránce nákupního košíku. Všechny tyto stránek sdílet běžné okno nejvyšší úrovně, což je okna prohlížeče. Je mapy uživatelského rozhraní pro jednotlivé stránky a třída nástroj má kód podobný následujícímu:  
  
```  
using ContosoProject.UIMaps;  
using ContosoProject.UIMaps.HomePageClasses;  
using ContosoProject.UIMaps.ProductPageClasses;  
using ContosoProject.UIMaps.ShoppingCartClasses;  
  
namespace ContosoProject  
{  
    public class TestRunUtility  
    {  
        // Private fields for the properties  
        private HomePage homePage = null;  
        private ProductPage productPage = null;  
        private ShoppingCart shoppingCart = null;  
  
        public TestRunUtility()  
        {  
            homePage = new HomePage();  
        }  
  
        // Properties that get each UI Map  
        public HomePage HomePage  
        {  
            get { return homePage; }  
            set { homePage = value; }  
        }  
  
        // Gets the ProductPage from the ProductPageMap.  
        public ProductPage ProductPageObject  
        {  
            get  
            {  
                if (productPage == null)  
                {  
                    // Instantiate a new page from the UI Map classes  
                    productPage = new ProductPage();  
  
                    // Since the Product Page and Home Page both use  
                    // the same browser page as the top level window,  
                    // get the top level window properties from the  
                    // Home Page.  
                    productPage.UIContosoFinalizeWindow.CopyFrom(  
                        HomePage.UIContosoWindowsIWindow);  
                }  
                return productPage;  
            }  
        }  
  
    // Continue to create properties for each page, getting the   
    // page object from the corresponding UI Map and copying the   
    // top level window properties from the Home Page.  
}  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>   
 <xref:Microsoft.VisualStudio.TestTools.UITesting.BrowserWindow.CopyFrom%2A>   
 [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)   
 [Vytváření programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate)   
 [Anatomie programového testu UI](../test/anatomy-of-a-coded-ui-test.md)
