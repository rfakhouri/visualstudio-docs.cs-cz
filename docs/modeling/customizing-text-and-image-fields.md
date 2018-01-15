---
title: "Přizpůsobení bitové kopie pole a Text | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d6bd4686565b24306d9c9565a5c4eddc65914f85
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="customizing-text-and-image-fields"></a>Přizpůsobení textových a obrazových polí
Když definujete dekoratéra text ve tvaru, je reprezentována TextField. Příklady inicializace TextFields a dalších ShapeFields zkontrolujte Dsl\GeneratedCode\Shapes.cs ve vašem řešení DSL.  
  
 TextField je objekt, který spravuje oblasti v rámci tvaru, jako je například místo přiřazené štítek. Jedna instance TextField jsou sdílena mezi mnoha tvarů stejné třídy. TextField instance neukládá text popisku samostatně pro každou instanci: místo toho `GetDisplayText(ShapeElement)` metoda přebírá jako parametr tvar a můžete vyhledat text závisí na aktuální stav tvaru a jeho element modelu.  
  
## <a name="how-the-appearance-of-a-text-field-is-determined"></a>Jakým způsobem je určován vzhled textové pole  
 `DoPaint()` Metoda je volána k zobrazení pole na obrazovce. Buď můžete přepsat výchozí `DoPaint(),` nebo můžete přepsat některé metody, které zavolá. Následující zjednodušenou verzi metody výchozí vám může pomoct pochopit, jak změnit výchozí chování:  
  
```  
// Simplified version:  
public override void DoPaint(DiagramPaintEventArgs e, ShapeElement parentShape)  
{   
  string text = GetDisplayText(shape);   
  StringFormat format = GetStringFormat(parentShape);  
  Brush brush = GetTextBrush(e.View, shape);  
  using (Font font = GetFont(shape))  
  {  
    e.Graphics.DrawString(text, font, brush, format);  
  }  
}  
// StringFormat determines whether the string is centered etc.  
// To customize statically for all instances of this shape field,   
// assign to DefaultStringFormat.  
// To customize dynamically or per shape, override this:    
public virtual StringFormat GetStringFormat(ShapeElement shape)  
{ return DefaultStringFormat; }  
  
// Override to customize the displayed string:  
public virtual string GetDisplayText(ShapeElement shape)  
{ return this.GetValue(shape).ToString(); }  
  
// Brush determines the text color.  
// To change the brush for every field, change the shape's styleset.   
// To customize to a brush in the style set, override GetTextBrushId.  
// To change the brush to non-standard color, override this.  
// Should take account of whether selected.   
public virtual Brush GetTextBrush(DiagramClientView view, ShapeElement shape)  
{ return shape.StyleSet.GetBrush(this.GetTextBrushId(view, shape)); }  
  
// Brush ID selects a brush from a StyleSet.  
// Either return a member of DiagramBrushes   
// or add your own brush to the shape or application's styleset.  
// Override this to change dynamically or per instance.  
// To change statically, just assign to default values.   
public virtual StyleSetResourceId GetTextBrushId(DiagramClientView view, ShapeElement shape)  
{ return IsSelected(view, shape) ? (view.Focused ? DefaultSelectedTextBrushId  
: DefaultInactiveSelectedTextBrushId ) : DefaultTextBrushId ;  
}  
  
// Font determines the shape and size of the text.  
// To change the font for every field, change the shape's styleset.   
// To customize to a font in the style set, override GetFontId.  
// To change the font to a non-standard font, override this.   
public virtual Font GetFont(ShapeElement shape)  
{ return shape.StyleSet.GetFont(GetFontId(shape)); }  
  
// Selects a font from a styleset.  
// Either return a member of DiagramFonts or   
// add your own font to the shape or application's styleset.  
// To change statically for all instances of this field,   
// assign to DefaultFontId.  
// To change per shape or dynamically, override this.   
public virtual StyleSetResourceId GetFontId(ShapeElement parentShape)  
{ return DefaultFontId; }  
  
```  
  
 Existuje několik párů z `Get` metody a `Default` vlastnosti, jako například `DefaultMultipleLine/GetMultipleLine()`. Výchozí vlastnosti chcete změnit hodnotu pro všechny instance pole tvaru můžete přiřadit hodnotu. Chcete-li hodnota se liší od jednoho obrazce instance do jiné nebo závisí na stavu tvaru nebo jeho element modelu, přepsat `Get` metoda.  
  
## <a name="static-customizations"></a>Statické přizpůsobení  
 Pokud chcete změnit všechny instance tohoto pole tvaru, nejdřív zjistěte, jestli můžete nastavit vlastnost v definici DSL. Můžete například nastavit velikost písma a stylu v okně Vlastnosti.  
  
 Pokud ne, pak mají přednost před `InitializeShapeFields` metoda třída shape a přiřadit hodnotu na odpovídající `Default...` vlastnost textové pole.  
  
> [!WARNING]
>  K přepsání `InitializeShapeFields()`, musíte nastavit **generuje dvojité odvozené** vlastnost třídy tvaru k `true` v definici DSL.  
  
 V tomto příkladu má obrazce textové pole, která se použije pro uživatele komentáře. Chceme používat standardní komentář písmo. Protože je standardní písmo ze sady styl, jsme můžete nastavit výchozí písma id:  
  
```  
  
 partial class ExampleShape  
{   protected override void InitializeShapeFields(IList<ShapeField> shapeFields)  
    {  
      // Fields set up according to DSL Definition:  
      base.InitializeShapeFields(shapeFields);  
      // Find and update comment field:  
      TextField commentField = ShapeElement.FindShapeField(shapeFields, "CommentDecorator") as TextField;  
      // Use the standard font for comments:  
      commentField.DefaultFontId = DiagramFonts.CommentText;  
  
```  
  
## <a name="dynamic-customizations"></a>Dynamické přizpůsobení  
 Chcete-li vzhled lišit závisí na stavu obrazce nebo jeho element modelu, odvozena vlastní podtřídou třídy `TextField` a přepište jeden nebo více `Get...` metody. Musíte také přepíše metodu InitializeShapeFields daný tvar a nahraďte instanci TextField instanci vlastní třídy.  
  
 Následující příklad vytvoří písmo textového pole závisí na stavu logické domény vlastnost modelu elementu obrazce.  
  
 Pokud chcete spustit tento příklad kódu, vytvořte nové řešení DSL pomocí minimální jazyka šablony. Přidání vlastnosti logické domény `AlternateState` k třídě ExampleElement domény. Přidejte do třídy ExampleShape dekoratéra na ikonu a nastavit jeho image do souboru bitové mapy. Klikněte na tlačítko **proveďte transformaci všech šablon**. Přidat nový soubor kódu v projektu DSL a vložte následující kód.  
  
 K testování kódu, stiskněte klávesu F5 a v ladění řešení, otevřete Ukázka diagramu. Výchozí stav ikonu by se zobrazit. Vyberte tvar a v okně vlastností změňte hodnotu **AlternateState** vlastnost. By se měl změnit písmo název elementu.  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
...  
  
  partial class ExampleShape  
  {  
    /// <summary>  
    /// Compose a list of the fields in this shape.  
    /// Called once for each shape class.  
    /// </summary>  
    protected override void InitializeShapeFields(IList<ShapeField> shapeFields)  
    {  
      // Fields set up according to DSL Definition:  
      base.InitializeShapeFields(shapeFields);  
      // Replace the text field for NameDecorator:  
      TextField oldField = ShapeElement.FindShapeField(shapeFields, "NameDecorator") as TextField;  
      shapeFields.Remove(oldField);  
      // Replace with my text field based on DSL Definition values:  
      MyTextField newField = new MyTextField(oldField);  
      shapeFields.Add(newField);  
    }  
  }  
  /// <summary>  
  /// Dynamic font depends on state of model element.  
  /// </summary>  
  public class MyTextField : TextField  
  {  
    public MyTextField(TextField prototype)  
      : base(prototype.Name)  
    {  
      DefaultText = prototype.DefaultText;  
      DefaultFocusable = prototype.DefaultFocusable;  
      DefaultAutoSize = prototype.DefaultAutoSize;  
      AnchoringBehavior.MinimumHeightInLines = prototype.AnchoringBehavior.MinimumHeightInLines;  
      AnchoringBehavior.MinimumWidthInCharacters = prototype.AnchoringBehavior.MinimumWidthInCharacters;  
      DefaultAccessibleState = prototype.DefaultAccessibleState;  
    }  
  
    public override System.Drawing.Font GetFont(ShapeElement parentShape)  
    {  
      // Access the Boolean domain property of the model element:  
      if ((parentShape.ModelElement as ExampleElement).AlternateState)  
        return new System.Drawing.Font("Callisto", 14.0f,  
               System.Drawing.FontStyle.Italic |   
               System.Drawing.FontStyle.Bold);  
      else  
        return base.GetFont(parentShape);  
    }  
  
  }  
  
```  
  
## <a name="style-sets"></a>Nastaví styl  
 Předchozí příklad ukazuje, jak můžete změnit textové pole na libovolného písma, která je k dispozici. Vhodnější než metoda je však změnit na jednu sadu stylů, která souvisí s tvar nebo s aplikací. Chcete-li to provést, přepište <xref:Microsoft.VisualStudio.Modeling.Diagrams.TextField.GetFontId%2A> nebo GetTextBrushId().  
  
 Případně, zvažte změnu sadu styl tvaru přepsáním <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.InitializeResources%2A>. To má za následek Změna písma a štětce u všech polí obrazce.  
  
## <a name="customizing-image-fields"></a>Přizpůsobení bitové kopie pole  
 Když definujete dekoratéra bitové kopie v obrazce a když definujete obrazce bitové kopie, oblasti, ve kterém se zobrazí tvar, který spravuje ImageField. Příklady inicializace ImageFields a dalších ShapeFields zkontrolujte Dsl\GeneratedCode\Shapes.cs ve vašem řešení DSL.  
  
 ImageField je objekt, který spravuje oblasti v rámci tvaru, jako je například místo přiřazené dekoratéra. Jedna instance třídy ImageField jsou sdílena mezi mnoha tvarů stejné třídy tvaru. Instance třídy ImageField neukládá samostatnou bitovou kopii pro každý tvar: místo toho `GetDisplayImage(ShapeElement)` metoda přebírá tvaru jako parametr a vyhledat bitovou kopii závisí na aktuální stav tvaru a jeho element modelu.  
  
 Pokud chcete zvláštní chování, například image, proměnné, můžete vytvořit vaše vlastní třídy odvozené od třídy ImageField.  
  
#### <a name="to-create-a-subclass-of-imagefield"></a>Chcete-li vytvořit podtřídou třídy ImageField  
  
1.  Nastavte **generuje dvojité odvozené** vlastnost nadřazené třídy tvaru v definici vaší DSL.  
  
2.  Přepsání `InitializeShapeFields` metoda třídě tvaru.  
  
    -   Vytvoření nového souboru kódu v projektu DSL a zápis třídu definice pro třídu tvaru. Přepsání definici metoda existuje.  
  
3.  Kontrola kódu `InitializeShapeFields` v DSL\GeneratedCode\Shapes.cs.  
  
     V způsob přepsání volat základní metodu a poté vytvořit instance třídy pole vlastní image. To použít k nahrazení v poli regulární bitové kopie `shapeFields` seznamu.  
  
## <a name="dynamic-icons"></a>Dynamické ikony  
 Tento příklad vytvoří ikonu změnit závisí na stavu element na obrazec modelu.  
  
> [!WARNING]
>  Tento příklad ukazuje, jak zajistit dekoratéra dynamické bitové kopie. Pokud chcete přepnout mezi jedno nebo dvě bitové kopie v závislosti na stavu modelu proměnné, je jednodušší vytvořit několik dekoratéry bitové kopie, vyhledejte je ve stejné pozici v tvaru a poté nastavit filtr viditelnost závislý na konkrétní hodnoty modelu, ale Proměnná. Pokud chcete nastavit tento filtr, vyberte obrazce mapy v definici DSL, otevřete okno Podrobnosti DSL a klikněte na kartu Dekorátory.  
  
 Pokud chcete spustit tento příklad kódu, vytvořte nové řešení DSL pomocí minimální jazyka šablony. Přidání vlastnosti logické domény `AlternateState` k třídě ExampleElement domény. Přidejte do třídy ExampleShape dekoratéra na ikonu a nastavit jeho image do souboru bitové mapy. Klikněte na tlačítko **proveďte transformaci všech šablon**. Přidat nový soubor kódu v projektu DSL a vložte následující kód.  
  
 K testování kódu, stiskněte klávesu F5 a v ladění řešení, otevřete Ukázka diagramu. Výchozí stav ikonu by se zobrazit. Vyberte tvar a v okně vlastností změňte hodnotu **AlternateState** vlastnost. Ikona by pak otočený do 90 stupňů, v tomto tvaru.  
  
```csharp  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
...  
partial class ExampleShape  
{  
    /// <summary>  
    /// Compose a list of the fields in this shape.  
    /// Called once for each shape class.  
    /// </summary>  
    /// <param name="shapeFields"></param>  
    protected override void InitializeShapeFields(IList<ShapeField> shapeFields)  
    {  
      // Fields set up according to DSL Definition:  
      base.InitializeShapeFields(shapeFields);  
  
      // Replace the image field:  
      ShapeField oldField = ShapeElement.FindShapeField(shapeFields, "IconDecorator");  
      shapeFields.Remove(oldField);  
      // Must keep the same name:  
      MyImageField newField = new MyImageField(oldField.Name);  
      shapeFields.Add(newField);  
      newField.DefaultImage = (oldField as ImageField).DefaultImage.Clone() as System.Drawing.Image;  
    }  
  }  
  
  public class MyImageField : ImageField  
  {  
    public MyImageField(string tag) : base(tag) { }  
  
    /// <summary>  
    /// Get the image for this field in the given shape.  
    /// </summary>  
    public override System.Drawing.Image GetDisplayImage(ShapeElement parentShape)  
    {  
      ExampleElement element = parentShape.ModelElement as ExampleElement;  
      if (element.AlternateState == true)  
        return AlternateImage;  
      else  
        return base.GetDisplayImage(parentShape);  
    }  
  
    private System.Drawing.Image alternateImage;  
    public System.Drawing.Image AlternateImage  
    {  
      get  
      {  
        if (alternateImage == null)  
        {  
          // Alternate image is a copy of the default, rotated by 90 degrees:  
          alternateImage = this.DefaultImage.Clone() as System.Drawing.Image;  
          alternateImage.RotateFlip(System.Drawing.RotateFlipType.Rotate90FlipNone);  
        }  
        return alternateImage;  
      }  
    }  
  }  
}  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Definování konektory a obrazců](../modeling/defining-shapes-and-connectors.md)   
 [Nastavení obrázek na pozadí v diagramu](../modeling/setting-a-background-image-on-a-diagram.md)   
 [Navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Zápis kódu pro úpravu jazyka specifického pro doménu](../modeling/writing-code-to-customise-a-domain-specific-language.md)