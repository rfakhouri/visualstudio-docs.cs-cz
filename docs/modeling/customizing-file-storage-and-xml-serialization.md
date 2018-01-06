---
title: "Přizpůsobení souboru úložiště a serializace XML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.dsldesigner.xmlbehavior
helpviewer_keywords: Domain-Specific Language, serialization
ms.assetid: 76c53ef1-e3b9-45da-b425-1bddb3c01395
caps.latest.revision: "17"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 850cb58f6763b521da9cdb1779b0960c0607ef88
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-file-storage-and-xml-serialization"></a>Přizpůsobení souborového úložiště a serializace XML
Když uživatel uloží instanci, nebo *modelu*, jazyka specifické pro doménu (DSL) v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], soubor XML se vytvoří nebo aktualizuje. Soubor můžete znovu k opětovnému vytvoření modelu v úložišti.  
  
 Schéma serializace můžete přizpůsobit úpravou nastavení v části **chování serializace Xml** v Průzkumníku DSL. Je uzel v rámci **chování serializace Xml** pro každou třídy domény, vlastnost a relace. Vztahy se nachází v jejich třídy zdroje. Existují také uzly odpovídající tvar, konektor a diagramu tříd.  
  
 Je také možné zapsat kód programu pro pokročilejší přizpůsobení.  
  
> [!NOTE]
>  Pokud chcete uložit model v určitém formátu, ale není potřeba ji znovu načíst formulář, zvažte použití textové šablony generovat výstup z modelu, místo schéma vlastní serializace. Další informace najdete v tématu [generování kódu z jazyka domény](../modeling/generating-code-from-a-domain-specific-language.md).  
  
## <a name="model-and-diagram-files"></a>Model a Diagram soubory  
 Každý model je obvykle uložen v dva soubory:  
  
-   Soubor modelu má název, například **Model1.mydsl**. Ukládají se zde prvků modelu a vztahy a jejich vlastnosti. Přípona souboru, jako **.mydsl** je dáno **FileExtension** vlastnost **Editor** uzlu v definici DSL.  
  
-   Soubor diagramu má název, například **Model1.mydsl.diagram**. Ukládají se obrazce, konektory a jejich pozic, barvy, tlouštěk čáry a další podrobnosti vzhled diagramu. Pokud uživatel odstraní **.diagram** soubor, základní informace v modelu není ztraceny. Rozložení diagramu bude ztracena. Po otevření souboru modelu výchozí nastavte tvarů a vytvoří se konektory.  
  
#### <a name="to-change-the-file-extension-of-a-dsl"></a>Chcete-li změnit příponu souboru DSL  
  
1.  Otevřete definici DSL. V Průzkumníku DSL klikněte na uzel Editor.  
  
2.  V okně vlastností upravit **FileExtension** vlastnost. Nezahrnovat počáteční "." přípony názvu souboru.  
  
3.  V Průzkumníku řešení, změňte název soubory šablon dvě položky v **DslPackage\ProjectItemTemplates**. Tyto soubory mají názvy, které mít tento formát:  
  
     `myDsl.diagram`  
  
     `myDsl.myDsl`  
  
## <a name="the-default-serialization-scheme"></a>Výchozí schéma serializace  
 Pokud chcete vytvořit příklad pro toto téma, byl použit následující definice DSL.  
  
 ![Diagram DSL definice & č. 45; Rodina stromu modelu](../modeling/media/familyt_person.png "FamilyT_Person")  
  
 Tato DSL byl použit pro vytvoření modelu, který má následující vzhled na obrazovce.  
  
 ![Rodina stromového diagramu, nástrojů a explorer](../modeling/media/familyt_instance.png "FamilyT_Instance")  
  
 Tento model byl uložit a znovu otevřít v textovém editoru XML:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<familyTreeModel xmlns:dm0="http://schemas.microsoft.com/VisualStudio/2008/DslTools/Core" dslVersion="1.0.0.0" Id="f817b728-e920-458e-bb99-98edc469d78f" xmlns="http://schemas.microsoft.com/dsltools/FamilyTree">  
  <people>  
    <person name="Henry VIII" birthYear="1491" deathYear="1547" age="519">  
      <children>  
        <personMoniker name="/f817b728-e920-458e-bb99-98edc469d78f/Elizabeth I" />  
        <personMoniker name="/f817b728-e920-458e-bb99-98edc469d78f/Mary" />  
      </children>  
    </person>  
    <person name="Elizabeth I" birthYear="1533" deathYear="1603" age="477" />  
    <person name="Mary" birthYear="1515" deathYear="1558" age="495" />  
  </people>  
</familyTreeModel>  
  
```  
  
 Všimněte si následující body týkající se serializovaných modelu:  
  
-   Každý uzel XML má název, který je stejný jako název třídy domény, s tím rozdílem, že počáteční písmeno je malá písmena. Například `familyTreeModel` a `person`.  
  
-   Vlastnosti domény, např. název a roknarozeni jsou serializovat jako atributy v uzlu XML. Počáteční znak název vlastnosti je znovu, převedený na malá písmena.  
  
-   Každý vztah je serializováno jako uzlu XML vnořit zdrojový konec relace. Uzel má stejný název jako zdrojová vlastnost roli, ale s počáteční znak malá písmena.  
  
     Například v definici DSL role, který je pojmenován **osoby** může mít původ v **FamilyTree** třídy.  V souboru XML, to je reprezentována uzlu s názvem `people` vnořené uvnitř `familyTreeModel` uzlu.  
  
-   Cílový element end každý vnoření relace je serializováno jako uzel vnořené v relaci. Například `people` uzel obsahuje několik `person` uzlů.  
  
-   Cílový element end relace každý odkaz je serializován jako *Přezdívka*, která kóduje odkaz na target element.  
  
     Například v položce `person` uzlu, může být `children` vztah. Tento uzel obsahuje zástupných názvů, jako:  
  
    ```  
    <personMoniker name="/f817b728-e920-458e-bb99-98edc469d78f/Elizabeth I" />  
    ```  
  
## <a name="understanding-monikers"></a>Principy Monikery  
 Monikery se používá k reprezentování křížové odkazy mezi různé části modelu a diagram souborů. Používají se také v `.diagram` soubor, který bude odkazovat na uzly v souboru modelu. Existují dvě formy Přezdívka:  
  
-   *ID monikery* quote GUID cílový element. Příklad:  
  
    ```  
    <personShapeMoniker Id="f79734c0-3da1-4d72-9514-848fa9e75157" />  
  
    ```  
  
-   *Kvalifikovaný klíče monikery* identifikovat cílový element posunut o hodnotu určenou doménou vlastnost s názvem klíče přezdívka. Přezdívka cílový element je předponu Přezdívka objektů svého nadřízeného elementu ve stromové struktuře vnoření vztahy.  
  
     Následující příklady jsou převzaty z DSL ve kterém existuje je třída domény s názvem alb, která vnoření vztah k doméně třídy s názvem skladbu:  
  
    ```  
    <albumMoniker title="/My Favorites/Jazz after Teatime" />  
    <songMoniker title="/My Favorites/Jazz after Teatime/Hot tea" />  
  
    ```  
  
     Kvalifikovaný klíče monikery bude použit, pokud cílové třídy obsahuje vlastnosti domény, jehož možnost **je klíč Přezdívka** je nastaven na `true` v **chování serializace Xml**. V příkladu se tato možnost nastavená pro vlastnosti domény s názvem "Title" v doméně třídy "Album" a "Skladeb".  
  
 Kvalifikovaný klíče monikery jsou jednodušší než ID monikery. Pokud máte v úmyslu XML modelu soubory číst pouze uživatelé, zvažte použití kvalifikovaného klíče zástupných názvů. Je však uživatel může nastavit více než jeden element mít stejný klíč přezdívka. Duplicitní klíče může způsobit, že soubor není znovu načíst správně. Proto pokud definujete domény třídu, která se odkazuje pomocí kvalifikovaný klíče zástupných názvů, měli byste zvážit způsobů, jak zabránit v uložení souboru, který má duplicitní monikery uživatele.  
  
#### <a name="to-set-a-domain-class-to-be-referenced-by-id-monikers"></a>Nastavení domény třídy bude odkazovat podle ID monikery  
  
1.  Ujistěte se, že **je klíč Přezdívka** je `false` pro každé domény vlastnost v třídě a jeho základních tříd.  
  
    1.  V Průzkumníku DSL rozbalte **Data Behavior\Class serializace Xml\\***\<třídě domény >***\Element Data**.  
  
    2.  Ověřte, že **je klíč Přezdívka** je `false` pro každou vlastnost domain.  
  
    3.  Pokud třída domény nemá základní třídu, opakujte postup uvedený v této třídě.  
  
2.  Nastavit **serializovat Id**  =  `true` pro třídu domény.  
  
     Tuto vlastnost lze nalézt v **chování serializace Xml**.  
  
#### <a name="to-set-a-domain-class-to-be-referenced-by-qualified-key-monikers"></a>Nastavení domény třídy bude odkazovat ve kvalifikovaný klíče monikery  
  
-   Nastavit **je klíč Přezdívka** pro vlastnost domain existující třídy domény. Typ vlastnosti musí být `string`.  
  
    1.  V Průzkumníku DSL rozbalte **Data Behavior\Class serializace Xml\\***\<třídě domény >***\Element Data**a pak vyberte Vlastnost Domain.  
  
    2.  V okně Vlastnosti nastavte **je klíč Přezdívka** k `true`.  
  
-   \-nebo –  
  
     Vytvořit nové třídy domény pomocí **třída s názvem domény** nástroj.  
  
     Tento nástroj vytvoří novou třídu, která má vlastnost domény s názvem název. **Název elementu, který je** a **je klíč Přezdívka** vlastností této vlastnosti domény jsou inicializována tak, aby `true`.  
  
-   \-nebo –  
  
     Vytvořte vztah dědičnosti ze třídy domény k jiné třídy, která má klíčovou vlastnost přezdívka.  
  
### <a name="avoiding-duplicate-monikers"></a>Zamezení duplicitní Monikery  
 Pokud chcete použít kvalifikovaný klíče zástupných názvů, je možné, že dva elementy v modelu uživatele může mít stejnou hodnotu v vlastnost klíče. Například pokud vaše DSL obsahuje třídu, osoba, která má vlastnost Name, uživatel může nastavit názvy dva elementy být stejné. I když modelu může být uloženy do souboru, se nebude znovu načíst správně.  
  
 Existuje několik metod, které se vyhnout této situaci:  
  
-   Nastavit **název elementu, který je**  =  `true` pro vlastnost klíče domény. Vyberte vlastnost domain v diagramu DSL definice a potom nastavte hodnotu v okně Vlastnosti.  
  
     Když uživatel vytvoří novou instanci třídy, tato hodnota vede domény vlastnost, která má být automaticky přiřadit jinou hodnotu. Výchozí chování přidá číslo na konec název třídy. To nezabrání uživatele změnit název na duplicitní, ale je stejně v případě, že když uživatel není nastavena hodnota před uložením modelu.  
  
-   Povolte ověřování DSL. V Průzkumníku DSL, vyberte Editor\Validation a nastavte **používá...**  vlastnosti, které chcete `true`.  
  
     Není ověření automaticky generované metoda, která kontroluje nejednoznačnosti. Metoda je `Load` ověření kategorie. Tím je zajištěno, že uživatel zobrazí upozornění, že nemusí být možné znovu otevřít soubor.  
  
     Další informace najdete v tématu [ověření v jazyce specifické pro doménu](../modeling/validation-in-a-domain-specific-language.md).  
  
### <a name="moniker-paths-and-qualifiers"></a>Přezdívka cesty a kvalifikátory.  
 Kvalifikovaný klíče Přezdívka končí Přezdívka klíč a je s předponou Přezdívka nadřazené ve stromové struktuře vnoření. Například, pokud je přezdívka Album:  
  
```  
<albumMoniker title="/My Favorites/Jazz after Teatime" />  
  
```  
  
 Potom může být jeden z skladeb nějž:  
  
```  
<songMoniker title="/My Favorites/Jazz after Teatime/Hot tea" />  
```  
  
 Ale pokud alb je odkazováno dle ID místo, pak zástupných názvů bude takto:  
  
```  
<albumMoniker Id="77472c3a-9bf9-4085-976a-d97a4745237c" />  
<songMoniker title="/77472c3a-9bf9-4085-976a-d97a4745237c/Hot tea" />  
```  
  
 Všimněte si, že je jedinečný identifikátor GUID je je nikdy předponu Přezdívka jeho nadřazený objekt.  
  
 Pokud znáte konkrétní domény vlastnost bude mít vždy hodnotu jedinečný v rámci modelu, můžete nastavit **je kvalifikátor Přezdívka** k `true` pro tuto vlastnost. To způsobí, že má být použit jako kvalifikátor, bez použití monikeru nadřazeného objektu. Nastavíte-li například **je kvalifikátor Přezdívka** a **je klíč Přezdívka** pro vlastnost domain Název třídy alb, název nebo identifikátor modelu nepoužívá v zástupných názvů pro alba a jeho embedded podřízené položky:  
  
```  
<albumMoniker name="Jazz after Teatime" />  
<songMoniker title="/Jazz after Teatime/Hot tea" />  
  
```  
  
## <a name="customizing-the-structure-of-the-xml"></a>Přizpůsobení strukturu XML  
 Chcete-li následující vlastní nastavení, rozbalte **chování serializace Xml** uzlu v Průzkumníku DSL. V části třídy domény rozbalte uzel elementu dat zobrazíte seznam vlastností a vztahů, které pocházejí na tuto třídu. Vyberte vztah a upravit její možnosti v okně Vlastnosti.  
  
-   Nastavit **vynechejte Element** jako pravdivý, aby vynechejte zdrojový uzel role, a seznamu cílové elementy. Neměli nastavte tuto možnost, pokud je více než jedna relace mezi zdrojové a cílové třídy.  
  
    ```  
  
    <familyTreeModel ...>  
      <!-- The following node is omitted by using Omit Element: -->  
      <!-- <people> -->  
        <person name="Henry VIII" .../>  
        <person name="Elizabeth I" .../>  
      <!-- </people> -->  
    </familyTreeModel>  
  
    ```  
  
-   Nastavit **použijte úplný formát** vložit cílové uzly do uzlů představující instance relace. Tato možnost nastavená automaticky, když přidáte do vztahu domény vlastnosti domény.  
  
    ```  
  
    <familyTreeModel ...>  
      <people>  
        <!-- The following node is inserted by using Use Full Form: -->  
        <familyTreeModelHasPeople myRelationshipProperty="x1">  
          <person name="Henry VIII" .../>  
        </familyTreeModelHasPeople>  
        <familyTreeModelHasPeople myRelationshipProperty="x2">  
          <person name="Elizabeth I" .../>  
        </familyTreeModelHasPeople>  
      </people>  
    </familyTreeModel>  
  
    ```  
  
-   Nastavit **reprezentace** = **Element** pomocí vlastnosti domény uložit jako element místo jako hodnota atributu.  
  
    ```  
    <person name="Elizabeth I" birthYear="1533">  
      <deathYear>1603</deathYear>  
    </person>  
    ```  
  
-   Chcete-li změnit pořadí, ve kterém se serializují atributy a relace, klikněte pravým tlačítkem na položku v rámci elementu Data a použijte **nahoru** nebo **přesunout dolů** příkazy nabídky.  
  
## <a name="major-customization-using-program-code"></a>Hlavní přizpůsobení pomocí kódu programu  
 Můžete nahradit části nebo všechny algoritmů serializace.  
  
 Doporučujeme, abyste si prostudovali kód v **Dsl\Generated Code\Serializer.cs** a **SerializationHelper.cs**.  
  
#### <a name="to-customize-the-serialization-of-a-particular-class"></a>Chcete-li přizpůsobit serializace určité třídy  
  
1.  Nastavit **je vlastní** v uzlu pro tuto třídu v rámci **chování serializace Xml**.  
  
2.  Proveďte transformaci všech šablon, sestavte řešení a prozkoumat výsledné chyby kompilace. Komentáře téměř všechny chybové vysvětlují, jaké kódu, je nutné zadat.  
  
#### <a name="to-provide-your-own-serialization-for-the-whole-model"></a>Poskytnout vlastní serializace pro celý model  
  
1.  Přepsání metody v Dsl\GeneratedCode\SerializationHelper.cs  
  
## <a name="options-in-xml-serialization-behavior"></a>Možnosti v chování serializace Xml  
 V Průzkumníku DSL uzlu chování serializace Xml obsahuje podřízený uzel pro každou třídy domény, vztah, tvaru, konektor a třída diagram. V každém z těchto uzlech je seznam vlastností a vztahů Source na daný element. Vztahy jsou reprezentované samy i v rámci své třídy zdroje.  
  
 Následující tabulka shrnuje možnosti, které můžete nastavit v této části DSL definice. V každém případě vybrat prvek v Průzkumníku DSL a nastavit možnosti v okně Vlastnosti.  
  
### <a name="xml-class-data"></a>Data XML – třída  
 Tyto prvky se nacházejí v Průzkumníku DSL pod **Data Behavior\Class serializace Xml**.  
  
|||  
|-|-|  
|Vlastnost|Popis|  
|Má schéma vlastního elementu.|V případě hodnoty True znamená, že má třída domény schéma vlastního elementu.|  
|Je vlastní|Tuto možnost nastavíte na **True** Pokud chcete napsat vlastní serializace a deserializace kód pro tuto třídu domény.<br /><br /> Sestavte řešení a zjistěte chyby chcete zjistit podrobné pokyny.|  
|Domény – třída|Třída domény, pro kterou platí tato třída datový uzel. Jen pro čtení.|  
|Název elementu|Název uzlu XML elementů této třídy. Výchozí hodnota je malá verzi třída názvu domény.|  
|Název atributu Přezdívka|Atribut použitý v elementech Přezdívka obsahovat odkaz na název. Pokud pole prázdné, použije se název klíčové vlastnosti nebo id.<br /><br /> V tomto příkladu je "name":`<personMoniker name="/Mike Nash"/>`|  
|Název elementu Přezdívka|Název elementu xml pro zástupných názvů, které odkazují na elementy této třídy.<br /><br /> Výchozí hodnota je malá verzi na konci "Přezdívka" název třídy. Například `personMoniker`.|  
|Název typu Přezdívka|Název typu xsd vygenerované monikery na elementy této třídy. XSD je v **Dsl\Generated kód\\\*Schema.xsd**|  
|Serialize – Id|V případě hodnoty True identifikátoru GUID elementu je součástí souboru. Toto musí být hodnota true, pokud není žádná vlastnost, která je označena **je klíč Přezdívka** a DSL definuje referenčních relací pro tuto třídu.|  
|Název typu|Název typu xml vygenerovaných xsd z třídy určené domény.|  
|Poznámky|Neformální poznámky související s tímto elementem|  
  
### <a name="xml-property-data"></a>Data XML – vlastnost  
 Vlastnost XML uzly se nacházejí v uzlu třídy.  
  
|||  
|-|-|  
|Vlastnost|Popis|  
|Vlastnost Domain|Vlastnost, pro kterou platí konfigurační data serializace xml. Jen pro čtení.|  
|Je přezdívka klíč|V případě hodnoty True, vlastnost se používá jako klíč pro vytvoření zástupných názvů, které odkazují na instance této třídy domény.|  
|Je přezdívka kvalifikátor|V případě hodnoty True, vlastnost slouží k vytváření kvalifikátor v zástupných názvů. Pokud je hodnota false, a pokud SerializeId není pro tuto třídu domény na hodnotu true, jsou monikery kvalifikovaný Přezdívka nadřazeného elementu ve stromové struktuře vnoření.|  
|Reprezentace|Pokud je atribut vlastnost serializovanou jako atribut xml; Pokud Element, jde serializovat jako element; Pokud ignorovat, nejde serializovat.|  
|Název XML|Název použité pro atribut xml nebo element reprezentující vlastnost. Ve výchozím nastavení to je malá verze vlastnost názvu domény.|  
|Poznámky|Neformální poznámky související s tímto elementem|  
  
### <a name="xml-role-data"></a>Data XML Role  
 Role datové uzly se nacházejí v rámci uzlů třída zdroje.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|Má vlastní Přezdívka|Nastavte na hodnotu true, pokud chcete poskytnout vlastní kód pro generování a řešení zástupných názvů, které překračují tuto relaci.<br /><br /> Podrobné pokyny sestavte řešení a pak dvakrát klikněte na chybové zprávy.|  
|Relace domény|Určuje relaci, na kterou se vztahují tyto možnosti. Jen pro čtení.|  
|Vynechat – Element|V případě hodnoty true je uzel XML, který odpovídá zdrojovou roli vynechaný schématu.<br /><br /> Pokud je více než jedna relace mezi zdrojové a cílové třídy, tento uzel role rozlišuje mezi odkazy, které patří do dvou relací. Proto doporučujeme tuto možnost v tomto případě nenastavujte.|  
|Název elementu role|Určuje název elementu XML, který je odvozený od zdrojovou roli. Výchozí hodnota je vlastnost název role.|  
|Použijte úplný formát|Je-li hodnotu true, každý target element nebo Přezdívka uzavřena v uzlu XML představující relace. Měla by být nastavena na hodnotu true, pokud relace má své vlastní domény vlastnosti.|  
  
## <a name="see-also"></a>Viz také  
 [Navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Vytváření kódu z jazyka specifického pro doménu](../modeling/generating-code-from-a-domain-specific-language.md)