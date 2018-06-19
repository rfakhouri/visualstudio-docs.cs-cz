---
title: Vytvoření testu webové služby v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, creating Web service tests
- Web services [Visual Studio ALM], creating
- service tests, Web
ms.assetid: fbcd57ee-06ad-4260-8694-09f8e0f93e39
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 2ae66ff032b3f43f80f8c00b12e2d344bba298b9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31970701"
---
# <a name="how-to-create-a-web-service-test"></a>Postupy: Vytvoření testu webové služby

Chcete-li testovat webové služby, lze použít test výkonnosti webu. Pomocí **vložit žádosti o** a **vložit požadavku webovou službu** možnosti, můžete přizpůsobit jednotlivých požadavků v **Editor testu výkonnosti webu** najít Web stránky služby. Ve webové aplikaci tyto stránky obvykle nejsou zobrazeny. Pro přístup k těmto stránkám je tedy nutné přizpůsobit požadavek.

Následující postupy používají webovou službu obsaženou v sadě Commerce Starter Kit. Si můžete stáhnout z [ASP.NET a obchodu Spojených států Starter Kit](http://go.microsoft.com/fwlink/?LinkId=181469).

 **Požadavky**

-   Visual Studio Enterprise

## <a name="to-test-a-web-service"></a>Testování webové služby

1.  Vytvořte nový webový test výkonu. Jakmile se prohlížeči se otevře, zvolte **Zastavit**.

2.  V **Editor testů výkonnosti webu**, klikněte pravým tlačítkem na test výkonnosti webu a vyberte **přidat požadavku webovou službu**.

3.  V **Url** vlastnost nový požadavek, zadejte název webové služby, například **http://localhost/storecsvs/InstantOrder.asmx**.

4.  Otevřete samostatné relaci prohlížeče a zadejte adresu URL stránky na .asmx **adresu** panelu nástrojů. Zvolte metodu, která má být testována, a prohlédněte si zprávu protokolu SOAP. Obsahuje hlavičku `SOAPAction`.

5.  V **Editor testu výkonnosti webu**, klikněte pravým tlačítkem na žádost a vyberte **přidat hlavičku** přidat novou hlavičkou. V **název** vlastnosti, typ `SOAPAction`. V **hodnotu** vlastnost, zadejte hodnotu, která se zobrazí v `SOAPAction`, jako například `"http://tempuri.org/CheckStatus"`.

6.  Rozbalte uzel adresy URL v editoru, zvolte **řetězec textu** uzel a **typ obsahu** vlastnost zadejte hodnotu `text/xml`.

7.  Přejděte zpět do prohlížeče v kroku 4, zvolte oddíl XML požadavku protokolu SOAP pro stránku popisu webové služby a zkopírujte jej do schránky.

8.  Obsah kódu XML je podobný následujícímu příkladu:

     ```xml
     <?xml version="1.0" encoding="utf-8"?>
     <soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
     <soap:Body>
       <CheckStatus xmlns="http://tempuri.org/">
         <userName>string</userName>
         <password>string</password>
         <orderID>int</orderID>
       </CheckStatus>
     </soap:Body>
     </soap:Envelope>
     ```

9. Vraťte se do **Editor testu výkonnosti webu** a klikněte na tlačítko se třemi tečkami (...) v **řetězec textu** vlastnost. Vložte obsah schránky do vlastnosti.

10. Aby test proběhl úspěšně, je zapotřebí všechny zástupné hodnoty v kódu XML nahradit platnými hodnotami. V předchozí ukázce by byly nahrazeny dvě instance typu `string` a jedna typu `int`. Tato operace webové služby bude dokončena pouze v případě, že existuje registrovaný uživatel, který provedl objednávku.

11. Klikněte pravým tlačítkem na žádosti webové služby a vyberte **přidat parametr řetězce dotazu URL**.

12. Parametru řetězce dotazu přiřaďte název a hodnotu. V předchozím příkladu je název `op` a hodnota je `CheckStatus`. Tím je identifikována operace webové služby, která má být provedena.

    > [!NOTE]
    > Datová vazba můžete použít v těle protokolu SOAP k nahrazení všech hodnotu zástupného symbolu pomocí hodnot data vázaná `{{DataSourceName.TableName.ColumnName}}` syntaxe.

13. Spuštění testu. V horním podokně Prohlížeče výsledků testu výkonnosti webu zvolte požadavek webové služby. V dolním podokně zvolte kartu Webový prohlížeč. Bude zobrazen kód XML vrácený webovou službou a výsledky všech operací.

## <a name="see-also"></a>Viz také

- [Vytvoření vlastního kódu a modulů Plugin pro zátěžové testy](../test/create-custom-code-and-plug-ins-for-load-tests.md)