---
title: Navrhování modelu připojení obchodních dat | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], designing a model
- Business Data Connectivity service [SharePoint development in Visual Studio], designing a model
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: bf2fd868927a7e8380d5c079c2f8dc86d5385961
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56628413"
---
# <a name="design-a-business-data-connectivity-model"></a>Navrhování modelu připojení obchodních dat
  Vývoj modelu služby připojení dat obchodní (BDC) přidáním entit a metody do souboru modelu. Popisuje, entita kolekce datových polí. Entity mohou například představovat tabulky v databázi. Metoda provede úlohu například přidávání, odstraňování nebo aktualizace dat reprezentovaný entity. Další informace najdete v tématu [integraci obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md).

## <a name="add-entities"></a>Přidání entit
 Entity můžete přidat přetažením nebo zkopírováním **Entity** ze sady Visual Studio **nástrojů** na návrháři služby BDC. Další informace najdete v tématu [jak: Přidání entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md).

 Definujte pole entity ve třídě. Můžete například přidat pole s názvem `Address` k `Customer` třídy. Můžete buď přidejte novou třídu do projektu, nebo použijte existující třídy vytvořené pomocí jiných nástrojů, jako je například Návrhář relací objektů (O/R Designer). Název entity a názvu třídy, která představuje entitu nemají tak, aby odpovídaly. Třída entity týkají definovat metody v modelu.

## <a name="add-methods"></a>Přidejte metody
 Když uživatelé zobrazit, přidat, aktualizovat nebo odstranit informace ze seznamu nebo webovou část, která je založená na modelu služby BDC volá metody v modelu. Model pro každý úkol, který může uživatel provádět, je nutné přidat metody. Vytvoření metod výběrem některé z pěti typů základní metoda z **podrobnosti metody služby BDC** okna. Následující tabulka popisuje pět základních metod modelu služby BDC.

|Metoda|Popis|
|------------|-----------------|
|Finder|Vrátí kolekci instancí entit. Volá se, když uživatel otevře seznamu nebo webovou část. Další informace najdete v tématu [jak: Přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md).|
|specifická metoda Finder|Vrátí instanci konkrétní entity. Volá se, když uživatel zobrazí podrobnosti o konkrétní položku v seznamu. Další informace najdete v tématu [jak: Přidání konkrétní vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md).|
|tvůrce|Přidá nová data do zdroje dat entity. Volá se, když se uživatelé rozhodnou **nová položka** tlačítko na pásu karet seznam, který je založen na modelu. Další informace najdete v tématu [jak: Přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md).|
|aktualizační metoda|Změní data v seznamu. Volá se, když uživatelé aktualizovat informace v seznamu. Další informace najdete v tématu [jak: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md).|
|metoda odstranění|Odebere data. Volá se, když uživatelé odstranit položku ze seznamu. Další informace najdete v tématu [jak: Přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md).|

## <a name="define-method-parameters"></a>Definovat parametry metody
 Když vytváříte metody, Visual Studio přidá vstupní a výstupní parametry, které jsou vhodné pro typ metody. Tyto parametry jsou pouze zástupné symboly. Ve většině případů je třeba upravit parametry tak, aby předat nebo správný typ vrácené hodnoty data. Ve výchozím nastavení, například vyhledávací metody vrátí řetězec. Ve většině případů budete chtít změnit návratový parametr metody Finder tak, že vrátí kolekci entit. Které můžete provést úpravou popisovače typu parametru. Typ popisovače je kolekce atributů, které popisují datový typ parametru. Další informace najdete v tématu [jak: Definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).

 Visual Studio umožňuje kopírovat popisovače typů mezi parametry v modelu. Například můžete třeba definovat popisovač typu s názvem `CustomerTD` pro návratový parametr `GetCustomer` metody. Můžete zkopírovat `CustomerTD` zadejte popisovač v **služby BDC Explorer**a následné vložení této popisovače typu na vstupní parametr `CreateCustomer` metody. Předchází se tak nebudou muset definovat stejný typ popisovače více než jednou.

## <a name="method-instances"></a>Instance metody
 Když vytváříte metody, Visual Studio přidá instance výchozí metody. Metoda instance je odkaz na metodu a výchozí hodnoty pro parametry. Jediná metoda může mít více instancí metody. Každá instance je kombinací podpisu metody a sadu výchozích hodnot. Další informace najdete v tématu [jak: Definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).

 Při spuštění projektu se zobrazí v rozevíracím seznamu výše Sharepointového seznamu Metoda instance. Uživatelé mohou zvolit metodu instance zobrazit data.

 Přidání výchozí hodnoty pro metodu instance, je třeba přímo upravit XML modelu. Další informace najdete v tématu [DefaultValue](http://go.microsoft.com/fwlink/?LinkID=169279).

## <a name="add-filter-descriptors"></a>Přidat deskriptory filtrů
 Příjemci modelu může být vhodné načítání instancí entity, které odpovídají kritérií. Pokud chcete povolit tuto funkci, můžete přidání deskriptoru filtru do metody. Deskriptory filtrů povolení příjemcům modelu k filtrování sady výsledků metodu předáním hodnoty metody předtím, než se provedou. Další informace najdete v tématu [jak: Přidat parametry filtrování operací pro omezení instancí z externího systému](http://go.microsoft.com/fwlink/?LinkID=169267).

 SharePoint poskytuje několik funkcí, které umožňují uživatelům zadávat hodnoty filtru. Například zadejte obchodní Data webové části textového pole filtru. Uživatelům můžete omezit data v seznamu tak, že zadáte hodnotu v textovém poli. Další informace o tom, jak přidat popisovač filtru na metodu, najdete v části [jak: Přidání deskriptoru filtru do vyhledávací metody](../sharepoint/how-to-add-a-filter-descriptor-to-a-finder-method.md).

### <a name="filter-descriptor-properties"></a>Popisovač vlastnosti filtru
 Musíte nastavit hodnotu **přidružené popisovače typu**, **název**, a **typ** vlastnosti popisovač filtru. Všechny ostatní vlastnosti jsou volitelné.

 **Přidružené popisovače typu** vlastnost se týká deskriptoru filtru do vstupního parametru. Když uživatel zadá hodnotu filtru, služba BDC předá tuto hodnotu do metody pomocí vstupního parametru.

 **Typ** vlastnost popisuje filtrování vzor, který chcete použít. Filtrování vzor, který jste vybrali v Sharepointu, ovlivňuje text, který se zobrazí v rozhraní uživatele (UI). Například pro filtrování vzor Komparátor, text **rovná** se zobrazí jako ovládací prvek výše obchodní Data webové části. Další informace o jednotlivých filtrování vzor, naleznete v tématu [typy filtry podporované službou BDC](http://go.microsoft.com/fwlink/?LinkId=169287).

 Další informace o vlastnostech popisovač filtru najdete v tématu [FilterDescriptor](http://go.microsoft.com/fwlink/?LinkID=169280).

### <a name="provide-default-values"></a>Zadejte výchozí hodnoty
 V některých případech se nemusí uživatel poskytnout hodnotu filtru. Výchozí hodnotu zadáte tak, že přidáte výchozí hodnotu pro instanci metody nebo tak, že nastavíte výchozí hodnotu v kódu metodu. Další informace o tom, jak přidat výchozí hodnotu pro instanci metody, naleznete v tématu [třídu MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282). Příklad toho, jak nastavit výchozí hodnotu vstupního parametru v kódu metodu, najdete v části [jak: Přidání deskriptoru filtru do vyhledávací metody](../sharepoint/how-to-add-a-filter-descriptor-to-a-finder-method.md).

## <a name="validate-the-model"></a>Ověření modelu
 Ověření modelu během vývoje. Visual Studio identifikuje problémy, které dokážou zabránit zahlcení modelu nechová podle očekávání. Tyto problémy se zobrazí v sadě Visual Studio **seznam chyb**.

 Model můžete ověřit tak, že otevřete místní nabídku pro návrháři služby BDC a následným výběrem možnosti **ověřit**. Pokud model obsahuje nějaké chyby, zobrazí se v **seznam chyb**. Můžete rychle přesunout kurzor na kód, který obsahuje chybu poklepáním na chybu v seznamu. Jako alternativu můžete použít **F8** nebo **Shift**+**F8** opakovaně krok vpřed nebo vzad přes chyby v seznamu klíčů.

 Pravidla modelu je porušena nějakým způsobem může dojít k chybě ověřování. Například pokud **IsCollection** typ popisovače je nastavena na **true**, ale neexistuje žádný podřízený typ popisovače, se zobrazí chyba ověření. Možná budete muset odkazovat na pravidla model služby BDC pochopit některé chyby, které se zobrazují v sadě Visual Studio **seznam chyb**. Další informace o pravidlech model služby BDC, naleznete v tématu [BDCMetadata schématu](http://go.microsoft.com/fwlink/?LinkID=169275).

## <a name="debug-the-solution-that-contains-the-model"></a>Ladění řešení, která obsahuje model
 Lze ladit kód, jako by ladění libovolného kódu v sadě Visual Studio. Na ladění vašeho kódu, nastavte zarážky kdekoli v kódu a pak spusťte ladicí program. Visual Studio otevře web služby SharePoint. V Sharepointu vytvořte seznam nebo webovou část, která používá vaše obchodní data. Potom můžete procházet kódem. Další informace o ladění projektů SharePoint naleznete v tématu [řešení potíží s SharePoint](../sharepoint/troubleshooting-sharepoint-solutions.md).

 Můžete také ladit kód v vlastní sestavení, které přidáte do projektu. Chcete-li ladit kód v vlastní sestavení, ale musíte přidat sestavení do balíčku řešení. Další informace najdete v tématu [jak: Přidání a odebrání dalších sestavení](../sharepoint/how-to-add-and-remove-additional-assemblies.md).

 Další informace o přidání vlastního sestavení do projektu naleznete v tématu [jak: Zahrnutí vlastního sestavení ve funkci BDC](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md).

### <a name="configure-bdc-security"></a>Konfigurace zabezpečení služby BDC
 Budete muset změnit nastavení zabezpečení ve službě SharePoint než můžete ladit vaše řešení. Ke změně tohoto nastavení, otevřete aplikaci služby Připojení obchodních dat v webu služby SharePoint 2010 centrální správy. V **nastavit oprávnění Store metadat** dialogovém okně Přidat uživatelský účet a pak vyberte některou z následujících možností:

|Úloha|Možnost|
|----------|------------|
|Chcete-li nasadit modely služby BDC.|Upravit|
|Chcete-li vytvořit seznamy a webové části pomocí externí typy obsahu (entity) v modelu.|Lze vybrat v klientech|
|Pokud chcete vytvořit, číst, aktualizovat a odstranit entity data.|Spuštění|

 Další informace o těchto nastaveních najdete v tématu [Správa služby Připojení obchodních dat](http://go.microsoft.com/fwlink/?LinkID=178883).

 Můžete také nastavit oprávnění zabezpečení pro jednotlivé modely nebo typy externího obsahu. Další informace o tom, jak nastavit oprávnění zabezpečení modelu najdete v tématu [správy modelu služby BDC](http://go.microsoft.com/fwlink/?LinkID=178884). Další informace o tom, jak nastavit oprávnění zabezpečení externího typu obsahu najdete v tématu [externího typu obsahu správu](http://go.microsoft.com/fwlink/?LinkID=178885).

> [!NOTE]
>  Pomocí těchto nastavení můžete ladit řešení na váš místní SharePoint Server. Další informace o tom, jak nakonfigurovat nastavení služby BDC týkající se zabezpečení na provozním serveru SharePoint, naleznete v tématu [Přehled zabezpečení služby Připojení obchodních dat](http://go.microsoft.com/fwlink/?LinkID=178886).

### <a name="retract-models-that-become-corrupt"></a>Odvolání modely, které poškozené
 Při prvním spuštění ladicího programu sady Visual Studio nasadí celý model do služby SharePoint. Pokaždé, když po tomto datu aktualizace nástroje Visual Studio modelu ve službě SharePoint obsahující všechny změny provedené mezi nasazeními.

 Můžou nastat situace, kde chcete Visual Studio a zcela odvolání modelu ze Sharepointu. Například modelu může být poškozen.  Chcete-li znovu nasaďte model na server SharePoint, nastavte **přírůstkové aktualizace** vlastnosti modelu, který má **False**, a pak spusťte ladicí program. **Přírůstkové aktualizace** vlastnost se zobrazí v **vlastnosti** okno při výběru uzlu, který představuje model v **služby BDC Explorer**. Ve výchozím nastavení, název modelu je **BdcModel1**.

### <a name="change-identifier-names-of-entities-in-the-model"></a>Změňte názvy identifikátorů entit v modelu
 Pokud změníte název identifikátoru po nasazení model, zobrazí se chyba nasazení. Nelze vyřešit tuto chybu tak, že nastavíte **přírůstkové aktualizace** vlastnosti modelu, který má **False**. Musíte ručně odvolání model a pak nasazení řešení. Další informace najdete v tématu [řešení potíží s SharePoint](../sharepoint/troubleshooting-sharepoint-solutions.md). Této chybě můžete předejít tak, že nastavíte **přírůstkové aktualizace** vlastnost **False** před počáteční nasazení modelu.

## <a name="locate-documentation-for-bdc-model-elements"></a>Vyhledání dokumentace k prvkům modelu služby BDC
 Visual Studio přidá XML element do modelu pro každou entitu, metodu nebo jinou položku, kterou vytvoříte. Atributy prvků se zobrazí jako vlastnosti **vlastnosti** okna. Informace o elementy a atributy, které sada Visual Studio generuje při návrhu modelu naleznete v tématu [BDCMetadata schématu](http://go.microsoft.com/fwlink/?LinkID=169275).

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Přehled nástroje pro navrhování modelů služby BDC](../sharepoint/bdc-model-design-tools-overview.md)|Popisuje nástroje, které vám umožní vizuálně navrhnout model pro BDC.|
|[Postupy: Přidání entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md)|Ukazuje, jak přidat typy externího obsahu nebo entity do modelu.|
|[Postupy: Přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)|Ukazuje, jak přidat metodu, která umožňuje uživatelům zobrazit v seznamu nebo webovou část Seznam entit.|
|[Postupy: Přidání konkrétní vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)|Ukazuje, jak přidat metodu, která umožňuje uživatelům zobrazit podrobnosti o konkrétní entity.|
|[Postupy: Přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)|Ukazuje, jak přidat metodu, která umožní uživatelům přidávat záznamy ke zdroji dat přímo ze seznamu nebo webovou část.|
|[Postupy: Přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)|Ukazuje, jak přidat metodu, která umožňuje uživatelům odebrat data ze zdroje dat pomocí možností v uživatelské rozhraní (UI) seznam nebo webovou část.|
|[Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)|Ukazuje, jak přidat metodu, která umožňuje uživatelům měnit záznamy ve zdroji dat přímo ze seznamu nebo webovou část.|
|[Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)|Ukazuje, jak přidat vstupní a vrátí parametry metody pomocí okna Podrobnosti metody v sadě Visual Studio.|
|[Postupy: Definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)|Ukazuje, jak definovat datové typy parametrů v modelu.|
|[Postupy: Definování instance metody](../sharepoint/how-to-define-a-method-instance.md)|Ukazuje, jak vytvořit instanci metody, které provádí služba BDC.|
|[Postupy: Přidání deskriptoru filtru do vyhledávací metody](../sharepoint/how-to-add-a-filter-descriptor-to-a-finder-method.md)|Ukazuje, jak povolit uživatelům k omezení počtu instancí vrácených vyhledávací metody.|
|[Vytváření přidružení mezi entitami](../sharepoint/creating-an-association-between-entities.md)|Popisuje, jak lze definovat vztahy mezi entitami v modelu. Obchodní Data webové části, seznam externích a vlastních aplikací můžete zobrazit tyto relace mezi daty v uživatelském rozhraní (UI).|
|[Postupy: Vytvoření přidružení mezi entitami](../sharepoint/how-to-create-an-association-between-entities.md)|Ukazuje, jak definovat vztahy mezi entitami v modelu.|
|[Návod: Createan externí seznam na Sharepointu s použitím obchodních dat](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)|Obsahuje podrobné pokyny, které ukazují, jak vytvářet a Testovat model, který se zobrazí v Sharepointovém seznamu externích kontaktů.|
|[Integrace obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)|Poskytuje přehled o vytváření a navrhování modelů služby BDC.|
