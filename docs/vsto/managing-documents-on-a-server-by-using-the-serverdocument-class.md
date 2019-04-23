---
title: Správa dokumentů na serveru s použitím třídy ServerDocument
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], managing on server
- Office documents [Office development in Visual Studio, managing on server
- ServerDocument class, managing documents on server
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 595c9127aad71cac6f446f356c309809b7172d94
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60045484"
---
# <a name="manage-documents-on-a-server-by-using-the-serverdocument-class"></a>Správa dokumentů na serveru s použitím třídy ServerDocument
  Můžete použít `ServerDocument` třídy v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] ke správě několik aspektů přizpůsobení na úrovni dokumentu i v případě, že není nainstalovaný Microsoft Office Word nebo Microsoft Office Excel. Můžete provádět následující úlohy:

- Přístup a úpravy dat v mezipaměti dat dokumentu nebo sešitu. Další informace najdete v tématu [pracovat s daty v mezipaměti v dokumentu](#CachedData).

- Správa vlastního nastavení sestavení, které je spojeno s dokumentem. Další informace najdete v tématu [spravovat dokumentu přizpůsobení](#CustomizationInfo).

  [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

## <a name="understand-the-serverdocument-class"></a>Pochopení třídy ServerDocument
 `ServerDocument` Třídy je určen k použití na počítačích, které nemají nainstalovaný Office. Proto je obvykle tuto třídu použít v aplikacích, které nejsou integrované se sadou Office, jako jsou projekty konzoly nebo projekty Windows Forms, nikoli projektech pro systém Office. Použití <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy v *Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll* sestavení.

 `ServerDocument` Třídy lze použít pro přizpůsobení na úrovni dokumentu, které byly vytvořeny pomocí [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)].

 Další informace o Visual Studio 2010 Tools pro systém Office Runtime, rozšíření Office pro rozhraní .NET Framework, naleznete v tématu [Visual Studio Tools for Office runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).

> [!NOTE]
>  Pokud máte starší verzi aplikace, která používá `ServerDocument` třídy v `Visual Studio Tools for Office` system (verze 3.0 Runtime), `Visual Studio Tools for Office` systém (verze 3.0 runtime) musí být nainstalován na počítačích, na kterých běží aplikace. `Visual Studio 2010 Tools for Office runtime` Nelze spustit tyto aplikace.

## <a name="CachedData"></a> Práce s data uložená v mezipaměti v dokumentu
 `ServerDocument` Třída obsahuje členy, které slouží k práci s mezipamětí dat v upravené dokumenty. Další informace o data uložená v mezipaměti, naleznete v tématu [ukládat data do mezipaměti](../vsto/caching-data.md) a [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).

 Následující tabulka uvádí členy, které můžete použít pro práci s data uložená v mezipaměti.

|Úloha|Člen použití|
|----------|-------------------|
|Chcete-li zjistit, jestli má dokument datové mezipaměti.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.IsCacheEnabled%2A> Metody.|
|Pro přístup k data uložená v mezipaměti v dokumentu.<br /><br /> Další informace najdete v tématu [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> Vlastnost.|

## <a name="CustomizationInfo"></a> Spravovat vlastní nastavení dokumentu
 Členy můžete použít `ServerDocument` třídy ke správě vlastního nastavení sestavení, které je spojeno s dokumentem. Například můžete programově odebrat vlastní nastavení z dokumentu tak, aby dokument už nejsou součástí přizpůsobení.

 Následující tabulka uvádí členy, které můžete použít ke správě vlastního nastavení sestavení.

|Úloha|Člen použití|
|----------|-------------------|
|Chcete-li zjistit, jestli dokument je součástí přizpůsobení na úrovni dokumentu.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.GetCustomizationVersion%2A> Metody.|
|Přizpůsobení programově připojit do dokumentu za běhu.<br /><br /> Další informace najdete v tématu [jak: Připojení rozšíření spravovaného kódu k dokumentům](../vsto/how-to-attach-managed-code-extensions-to-documents.md)|Jeden z <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> metody.|
|Odebrat vlastní nastavení z dokumentu prostřednictvím kódu programu za běhu.<br /><br /> Další informace najdete v tématu [jak: Odebrání rozšíření spravovaného kódu z dokumentů](../vsto/how-to-remove-managed-code-extensions-from-documents.md).|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> Metody.|
|Získat adresu URL manifestu nasazení, který je přidružený k dokumentu.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.DeploymentManifestUrl%2A> Vlastnost.|

## <a name="see-also"></a>Viz také:
- [Postupy: Připojení rozšíření spravovaného kódu k dokumentům](../vsto/how-to-attach-managed-code-extensions-to-documents.md)
- [Postupy: Odebrání rozšíření spravovaného kódu z dokumentů](../vsto/how-to-remove-managed-code-extensions-from-documents.md)
- [Visual Studio Tools for Office runtime – přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md)
- [Data v mezipaměti](../vsto/caching-data.md)
