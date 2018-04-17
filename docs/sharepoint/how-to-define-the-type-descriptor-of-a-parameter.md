---
title: 'Postupy: definování deskriptoru typu pro parametr | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], type descriptor
- BDC [SharePoint development in Visual Studio], parameter types
- BDC [SharePoint development in Visual Studio], type descriptor
- Business Data Connectivity service [SharePoint development in Visual Studio], parameter types
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6ebdd8e968d631cf1d53515449c7e705c2978087
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-define-the-type-descriptor-of-a-parameter"></a>Postupy: Definování deskriptoru typu pro parametr
  Popisovač typu obsahuje vlastnosti, které popisují datový typ parametru. Popisovač typu můžete definovat pole, entity nebo kolekci entit. Další informace najdete v tématu [TypeDescriptor](http://msdn.microsoft.com/library/ms543392%28v=office.12%29.aspx).  
  
### <a name="to-define-the-type-descriptor-of-a-parameter"></a>K definování deskriptoru typu pro parametr  
  
1.  V **podrobnosti o metodě BDC** okně zvolte popisovač typu parametru.  
  
2.  Na řádku nabídek zvolte **zobrazení**, **vlastnosti – okno**.  
  
3.  V **vlastnosti** nastavte vlastnosti popisovač typu.  
  
     Následující postupy popisují, jak definovat popisovač typu jako kolekce pole, entity nebo entity.  
  
### <a name="to-define-a-field"></a>Chcete-li definovat pole  
  
1.  V **vlastnosti** nastavte **název** vlastnost na název pole v typu, který představuje entitu popisovač typu (například: **FirstName**).  
  
2.  V seznamu vedle položky **TypeName** vlastnosti, vyberte příslušný datový typ (například **Int32**).  
  
     Informace o další volitelné parametry najdete v tématu [TypeDescriptor](http://msdn.microsoft.com/library/ms543392%28v=office.12%29.aspx).  
  
### <a name="to-define-an-entity"></a>Chcete-li definovat entity  
  
1.  V **vlastnosti** nastavte **název** vlastnost, která má název, který popisuje entity (například: **kontaktujte**).  
  
2.  Nastavte **TypeName** na plně kvalifikovaný název typu, který představuje entitu. Tento typ může být třídu v projektu, typu definované v sestavení, na kterou odkazujete v řešení nebo typem definovaným v modelu služby BDC objektu.  
  
    -   Pro třídu do projektu, vyberte na šipku dolů vedle **TypeName** vlastnosti, vyberte **aktuálního projektu** v dialogovém okně, které se zobrazí a potom vyberte třídu do projektu.  
  
         Plně kvalifikovaný název obsahuje obor názvů a název třídy, za nímž následuje název systému LOB. Nastaví hodnotu v následujícím příkladu **TypeName** vlastnost třídy ve vašem projektu.  
  
         `MyBDCNamespace.BdcModel1.Contact, BdcModel1`  
  
    -   Pro typ umístěn v sestavení ve vašem řešení plně kvalifikovaný název obsahuje název typu, název sestavení, číslo verze, jazykové verze a token veřejného klíče.  
  
         Nastaví hodnotu v následujícím příkladu **TypeName** vlastnost typu definované v sestavení, na kterou odkazujete v řešení.  
  
         `MyNamespace.Contact, myAssemblyName, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
    -   Pro typ definované v objektu modelu služby BDC obsahuje plně kvalifikovaný název oboru názvů a název typu.  
  
         Nastaví hodnotu v následujícím příkladu **TypeName** vlastnosti na typ v modelu služby BDC objektu.  
  
         `Microsoft.BusinessData.Runtime.DynamicType`  
  
3.  V **podrobnosti o metodě BDC** oken, otevřete seznam, který se zobrazí pro popisovač typu a potom zvolte **upravit**.  
  
     **Průzkumník modelu BDC** otevře se okno.  
  
4.  V **Průzkumník modelu BDC**, otevřete v místní nabídce popisovač typu a potom zvolte **přidat popisovač typu**.  
  
     Nový popisovač typu je přidán jako podřízený do popisovače typu entity. Tento popisovač typu nakonfigurujte jako pole.  
  
5.  Opakujte krok 4 pro přidání podřízené popisovač typu pro každé pole entity.  
  
### <a name="to-define-a-collection-of-entities"></a>Chcete-li definovat kolekci entit  
  
1.  V **podrobnosti o metodě BDC** okně zvolte deskriptoru typu pro parametr, který chcete.  
  
2.  Na řádku nabídek zvolte **zobrazení**, **vlastnosti – okno**.  
  
3.  V **vlastnosti** nastavte **název** vlastnost, která má název, který popisuje entity (například: **kontakty**).  
  
4.  Nastavte **IsCollection** vlastnost **True**. To znamená, že je tento popisovač typu kolekce entit.  
  
5.  Nastavte **TypeName** na řetězec, který obsahuje odkaz na vlastnost <xref:System.Collections.Generic.IEnumerable%601> rozhraní a plně kvalifikovaný název typu, který představuje entitu. Tento typ může být třídu v projektu, typu definované v sestavení, na kterou odkazujete v řešení nebo typem definovaným v modelu služby BDC objektu.  
  
    -   Pro třídu do projektu, vyberte na šipku dolů vedle **TypeName** vlastnosti, vyberte **aktuálního projektu** v dialogovém okně, které se zobrazí a potom vyberte třídu do projektu.  
  
         Plně kvalifikovaný název obsahuje obor názvů a název třídy, za nímž následuje název systému LOB.  
  
         Nastaví hodnotu v následujícím příkladu **TypeName** vlastnost kolekce tříd ve vašem projektu.  
  
         `System.Collections.Generic.IEnumerable`1 [MyBDCNamespace.` ` BdcModel1.Contact, BdcModel1].  
  
    -   Pro typ umístěn v sestavení ve vašem řešení plně kvalifikovaný název obsahuje název typu, název sestavení, číslo verze, jazykové verze a token veřejného klíče.  
  
         Nastaví hodnotu v následujícím příkladu **TypeName** vlastnost, která má kolekci typů v sestavení, na kterou odkazujete v řešení.  
  
         `System.Collections.Generic.IEnumerable`1 [MyNamespace.Contact, myAssemblyName, verze = 4.0.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089].  
  
    -   Pro typ definované v objektu modelu služby BDC plně kvalifikovaný název obsahuje jenom obor názvů a název typu.  
  
         Nastaví hodnotu v následujícím příkladu **TypeName** vlastnost typy definované v objektu modelu služby BDC do kolekce.  
  
         `System.Collections.Generic.IEnumerable`1 [Microsoft.BusinessData.Runtime.DynamicType].  
  
6.  V **podrobnosti o metodě BDC** oken, otevřete seznam, který se zobrazí pro popisovač typu a potom zvolte **upravit**.  
  
     **Průzkumník modelu BDC** otevře se okno.  
  
7.  V **Průzkumník modelu BDC**, otevřete v místní nabídce popisovač typu a potom zvolte **přidat popisovač typu**.  
  
     Nový popisovač typu je přidán jako podřízený do popisovače typu kolekce. Tento popisovač typu nakonfigurujte jako entity.  
  
## <a name="see-also"></a>Viz také  
 [Přehled nástrojů pro navrhování modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md)   
 [Postupy: Přidání Entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Postupy: definování Instance metody](../sharepoint/how-to-define-a-method-instance.md)   
 [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  