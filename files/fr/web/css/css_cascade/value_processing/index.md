---
title: Valeur calculée
slug: Web/CSS/CSS_cascade/Value_processing
original_slug: Web/CSS/computed_value
---

{{CSSRef}}

La **valeur calculée** d'une propriété CSS est calculée à partir de [la valeur définie](/fr/docs/Web/CSS/specified_value) :

1. En gérant les valeurs spéciales {{cssxref("inherit")}}, {{cssxref("initial")}}, {{cssxref("unset")}} et {{cssxref("revert")}}.
2. En effectuant les calculs décrits dans la section « Valeur calculée » de chaque résumé de propriété.

Les calculs utilisés pour obtenir la **valeur calculée** correspondent généralement à la conversion des valeurs relatives (exprimées dans des unités relatives comme `em` ou en pourcentages) en valeur absolue. Ainsi, si un élément possède les valeurs spécifiées suivantes `font-size: 16px` et `padding-top: 2em`. La valeur calculée de la propriété `padding-top` sera `32px` (on double la taille de la police).

Cependant, pour certaines propriétés (celles où les pourcentages sont relatifs à quelque chose lié à la disposition comme `width`, `margin-right`, `text-indent`, et `top`), les valeurs spécifiées exprimées en pourcentages deviennent des valeurs calculées exprimées en pourcentages. De plus, les nombres sans unité utilisés pour la propriété `line-height` sont également utilisés comme valeurs calculées. Ces valeurs relatives sont résolues en valeurs absolues lorsqu'on détermine [les valeurs utilisées](/fr/docs/Web/CSS/used_value).

Le principal intérêt de la valeur calculée (en dehors de la gestion du passage de [la valeur spécifiée](/fr/docs/Web/CSS/specified_value) à [la valeur utilisée](/fr/docs/Web/CSS/used_value)) est [l'héritage](/fr/docs/Web/CSS/Inheritance), notamment grâce au mot-clé {{cssxref("inherit")}}.

> [!NOTE]
> La méthode du DOM {{domxref("Window.getComputedStyle", "getComputedStyle()")}} renvoie [la valeur résolue](/fr/docs/Web/CSS/resolved_value) qui correspond à la valeur calculée ou à [la valeur utilisée](/fr/docs/Web/CSS/used_value) selon la propriété.

## Spécifications

{{Specifications}}

## Voir aussi

- [La référence CSS](/fr/docs/Web/CSS/Reference)
- [La notion de valeur initiale](/fr/docs/Web/CSS/initial_value)
- [La notion de valeur définie](/fr/docs/Web/CSS/specified_value)
- [La notion de valeur calculée](/fr/docs/Web/CSS/computed_value)
- [La notion de valeur utilisée](/fr/docs/Web/CSS/used_value)
- [La notion de valeur résolue](/fr/docs/Web/CSS/resolved_value)
- [La notion de valeur réelle](/fr/docs/Web/CSS/actual_value)
- {{cssxref("inherit")}}
- {{cssxref("initial")}}
- {{cssxref("unset")}}
- {{cssxref("revert")}}
- {{domxref("window.getComputedStyle")}}
