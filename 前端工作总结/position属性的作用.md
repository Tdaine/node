## position属性的作用

position属性用来指定一个元素在网页上的位置，有五种定位方式

* static
* relative
* fixed
* absolute
* sticky

**static属性值**

是position的默认值，正常的页面流，浏览器会按照源码的顺序决定元素的位置。

注意：static定位所导致的元素位置，是浏览器自主决定的，所以这时top、bottom、left、right这四个属性无效

**relative，absolute，fixed**

这三个属性值都有一个共同点，都是相对于某个基点的定位，不同之处仅仅在于基点不同。

这三个元素都不会对其他元素的位置产生影响，所以元素之间可能产生重叠

**relative属性值**

relative表示，相对于默认值（即static时的位置）进行偏移，即定位基点是元素的默认位置

必须搭配top、bottom、left、right这四个属性一起使用，用来指定偏移的方向和距离

```css
div {
	position: relative;
	top: 10px;	//向下偏于10px
}
```

**absolute属性**

absolute表示，相对于上级元素(一般是父级元素)进行偏移，定位基点是父元素

限制：定位基点不能是static定位，否则定位基点就会变成整个网页的根元素html。

​			必须搭配top、bottom、left、right这四个属性一起使用

```html
html代码
<div id="father">
	<div id="son"></div>
</div>

#father {
	position: relative;
}
#son {
	position: absolute;
	top: 20px
}
```

在上面代码中，父元素是relative定位，子元素是absolute定位，所以子元素的定位基点就是父元素，相对于父元素向下偏移20px。如果父元素是static定位，上例中的子元素就是相对于网页的顶部向下偏移20px

**fixed属性值**

fixed表示，相对于视口进行偏移，即定位基点是浏览器窗口。所以就是使元素的位置不随页面滚动而变化，好像固定到网页一样。

搭配top、bottom、left、right这四个属性一起使用，表示元素的初始位置是基于视口计算的，否则初始位置就是元素的默认位置。

```css
div {
	position: fixed;
	top: 0;
}
```

上面代码中，div元素始终在视口顶部，不随网页滚动而变化

**sticky属性值**

sticky像是relative和fixed的结合；有时是relative定位（基于自身默认位置），另一些时候视fixed定位（定位基于视口）

比如拉动网页的滚动条，工具栏始终在页面头部

等页面重新向上滚动到原位，工具栏也会回到默认位置。

sticky生效的前提是，必须搭配top、bottom、left、right这四个属性一起使用。

具体规则是：当页面滚动，父元素开始脱离视口时，只要sticky元素的距离达到生效门槛（就是设置的距离），relative定位自动切换为fixed定位；等到父元素完全脱离视口时，fixed定位自动切换回relative定位。

网上一个现场的例子：

[demo](https://css-tricks.com/position-sticky-and-table-headers/)

HTML

```html
<table>
  <thead>
    <tr class="red">
      <th>Name</th>
      <th>Age</th>
      <th>Job</th>
      <th>Color</th>
      <th>URL</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Lorem.</td>
      <td>Ullam.</td>
      <td>Vel.</td>
      <td>At.</td>
      <td>Quis.</td>
    </tr>
    <tr>
      <td>Quas!</td>
      <td>Velit.</td>
      <td>Quisquam?</td>
      <td>Rerum?</td>
      <td>Iusto?</td>
    </tr>
    <tr>
      <td>Voluptates!</td>
      <td>Fugiat?</td>
      <td>Alias.</td>
      <td>Doloribus.</td>
      <td>Veritatis.</td>
    </tr>
    <tr>
      <td>Maiores.</td>
      <td>Ab.</td>
      <td>Accusantium.</td>
      <td>Ullam!</td>
      <td>Eveniet.</td>
    </tr>
    <tr>
      <td>Hic.</td>
      <td>Id!</td>
      <td>Officiis.</td>
      <td>Modi!</td>
      <td>Obcaecati.</td>
    </tr>
    <tr>
      <td>Soluta.</td>
      <td>Ad!</td>
      <td>Impedit.</td>
      <td>Alias!</td>
      <td>Ad.</td>
    </tr>
    <tr>
      <td>Expedita.</td>
      <td>Quo.</td>
      <td>Exercitationem!</td>
      <td>Optio?</td>
      <td>Ipsum?</td>
    </tr>
    <tr>
      <td>Commodi!</td>
      <td>Rem.</td>
      <td>Aspernatur.</td>
      <td>Accusantium!</td>
      <td>Maiores.</td>
    </tr>
    <tr>
      <td>Omnis.</td>
      <td>Cumque?</td>
      <td>Eveniet!</td>
      <td>Mollitia?</td>
      <td>Vero.</td>
    </tr>
    <tr>
      <td>Error!</td>
      <td>Inventore.</td>
      <td>Quasi!</td>
      <td>Ducimus.</td>
      <td>Repudiandae!</td>
    </tr>
    <tr>
      <td>Dolores!</td>
      <td>Necessitatibus.</td>
      <td>Corrupti!</td>
      <td>Eum.</td>
      <td>Sunt!</td>
    </tr>
    <tr>
      <td>Ea.</td>
      <td>Culpa?</td>
      <td>Quam?</td>
      <td>Nemo!</td>
      <td>Sit!</td>
    </tr>
    <tr>
      <td>Veritatis!</td>
      <td>Facilis.</td>
      <td>Expedita?</td>
      <td>Ipsam!</td>
      <td>Omnis!</td>
    </tr>
    <tr>
      <td>Vitae.</td>
      <td>Cumque.</td>
      <td>Repudiandae.</td>
      <td>Ut?</td>
      <td>Sed!</td>
    </tr>
    <tr>
      <td>Accusantium.</td>
      <td>Adipisci.</td>
      <td>Sit.</td>
      <td>Maxime.</td>
      <td>Harum.</td>
    </tr>
    <tr class="green">
      <th>Name</th>
      <th>Age</th>
      <th>Job</th>
      <th>Color</th>
      <th>URL</th>
    </tr>
    <tr>
      <td>Qui!</td>
      <td>Accusamus?</td>
      <td>Minima?</td>
      <td>Dolorum.</td>
      <td>Molestiae.</td>
    </tr>
    <tr>
      <td>Vero!</td>
      <td>Voluptatum?</td>
      <td>Ea?</td>
      <td>Odit!</td>
      <td>A.</td>
    </tr>
    <tr>
      <td>Debitis.</td>
      <td>Veniam.</td>
      <td>Fuga.</td>
      <td>Alias!</td>
      <td>Recusandae!</td>
    </tr>
    <tr>
      <td>Aperiam!</td>
      <td>Dolorum.</td>
      <td>Enim.</td>
      <td>Sapiente!</td>
      <td>Suscipit?</td>
    </tr>
    <tr>
      <td>Consequuntur.</td>
      <td>Doloremque.</td>
      <td>Illum!</td>
      <td>Iste!</td>
      <td>Sint!</td>
    </tr>
    <tr>
      <td>Facilis.</td>
      <td>Error.</td>
      <td>Fugiat.</td>
      <td>At.</td>
      <td>Modi?</td>
    </tr>
    <tr>
      <td>Voluptatibus!</td>
      <td>Alias.</td>
      <td>Eaque.</td>
      <td>Cum.</td>
      <td>Ducimus!</td>
    </tr>
    <tr>
      <td>Nihil.</td>
      <td>Enim.</td>
      <td>Earum?</td>
      <td>Nobis?</td>
      <td>Eveniet.</td>
    </tr>
    <tr>
      <td>Eum!</td>
      <td>Id?</td>
      <td>Molestiae.</td>
      <td>Velit.</td>
      <td>Minima.</td>
    </tr>
    <tr>
      <td>Sapiente?</td>
      <td>Neque.</td>
      <td>Obcaecati!</td>
      <td>Earum.</td>
      <td>Esse.</td>
    </tr>
    <tr>
      <td>Nam?</td>
      <td>Ipsam!</td>
      <td>Provident.</td>
      <td>Ullam.</td>
      <td>Quae?</td>
    </tr>
    <tr>
      <td>Amet!</td>
      <td>In.</td>
      <td>Officia!</td>
      <td>Natus?</td>
      <td>Tempore?</td>
    </tr>
    <tr>
      <td>Consequatur.</td>
      <td>Hic.</td>
      <td>Officia.</td>
      <td>Itaque?</td>
      <td>Quasi.</td>
    </tr>
    <tr>
      <td>Enim.</td>
      <td>Tenetur.</td>
      <td>Asperiores?</td>
      <td>Eos!</td>
      <td>Libero.</td>
    </tr>
    <tr>
      <td>Exercitationem.</td>
      <td>Quidem!</td>
      <td>Beatae?</td>
      <td>Adipisci?</td>
      <td>Accusamus.</td>
    </tr>
    <tr>
      <td>Omnis.</td>
      <td>Accusamus?</td>
      <td>Eius!</td>
      <td>Recusandae!</td>
      <td>Dolor.</td>
    </tr>
    <tr>
      <td>Magni.</td>
      <td>Temporibus!</td>
      <td>Odio!</td>
      <td>Odit!</td>
      <td>Voluptatum?</td>
    </tr>
    <tr>
      <td>Eum.</td>
      <td>Animi!</td>
      <td>Labore.</td>
      <td>Alias!</td>
      <td>Fuga.</td>
    </tr>
    <tr>
      <td>Quia!</td>
      <td>Quis.</td>
      <td>Neque?</td>
      <td>Illo.</td>
      <td>Ad.</td>
    </tr>
    <tr>
      <td>Officiis.</td>
      <td>Exercitationem!</td>
      <td>Adipisci?</td>
      <td>Officiis?</td>
      <td>In?</td>
    </tr>
    <tr>
      <td>Voluptates?</td>
      <td>Voluptatum.</td>
      <td>Nihil.</td>
      <td>Totam?</td>
      <td>Quisquam!</td>
    </tr>
    <tr>
      <td>Soluta.</td>
      <td>Tempore!</td>
      <td>Cupiditate.</td>
      <td>Beatae.</td>
      <td>Perspiciatis.</td>
    </tr>
    <tr>
      <td>Porro.</td>
      <td>Officia?</td>
      <td>Error.</td>
      <td>Culpa?</td>
      <td>Fugit.</td>
    </tr>
    <tr>
      <td>Et?</td>
      <td>Nemo.</td>
      <td>Nisi?</td>
      <td>Totam!</td>
      <td>Voluptate.</td>
    </tr>
    <tr>
      <td>Saepe?</td>
      <td>Vero.</td>
      <td>Amet?</td>
      <td>Illo!</td>
      <td>Laborum!</td>
    </tr>
    <tr class="purple">
      <th>Name</th>
      <th>Age</th>
      <th>Job</th>
      <th>Color</th>
      <th>URL</th>
    </tr>
    <tr>
      <td>Atque!</td>
      <td>Tenetur.</td>
      <td>Optio.</td>
      <td>Iure.</td>
      <td>Porro.</td>
    </tr>
    <tr>
      <td>Atque.</td>
      <td>Alias.</td>
      <td>Doloremque.</td>
      <td>Velit.</td>
      <td>Culpa.</td>
    </tr>
    <tr>
      <td>Placeat?</td>
      <td>Necessitatibus.</td>
      <td>Voluptate!</td>
      <td>Possimus.</td>
      <td>Nam?</td>
    </tr>
    <tr>
      <td>Illum!</td>
      <td>Quae.</td>
      <td>Expedita!</td>
      <td>Omnis.</td>
      <td>Nam.</td>
    </tr>
    <tr>
      <td>Consequuntur!</td>
      <td>Consectetur!</td>
      <td>Provident!</td>
      <td>Consequuntur!</td>
      <td>Distinctio.</td>
    </tr>
    <tr>
      <td>Aperiam!</td>
      <td>Voluptatem.</td>
      <td>Cupiditate!</td>
      <td>Quae.</td>
      <td>Praesentium.</td>
    </tr>
    <tr>
      <td>Possimus?</td>
      <td>Qui.</td>
      <td>Consequuntur.</td>
      <td>Deleniti.</td>
      <td>Voluptas.</td>
    </tr>
    <tr>
      <td>Hic?</td>
      <td>Ab.</td>
      <td>Asperiores?</td>
      <td>Omnis.</td>
      <td>Animi!</td>
    </tr>
    <tr>
      <td>Cupiditate.</td>
      <td>Velit.</td>
      <td>Libero.</td>
      <td>Iste.</td>
      <td>Dicta?</td>
    </tr>
    <tr>
      <td>Consequatur!</td>
      <td>Nobis.</td>
      <td>Aperiam!</td>
      <td>Odio.</td>
      <td>Nemo!</td>
    </tr>
    <tr>
      <td>Dolorem.</td>
      <td>Distinctio?</td>
      <td>Provident?</td>
      <td>Nisi!</td>
      <td>Impedit?</td>
    </tr>
    <tr>
      <td>Accusantium?</td>
      <td>Ea.</td>
      <td>Doloribus.</td>
      <td>Nobis.</td>
      <td>Maxime?</td>
    </tr>
    <tr>
      <td>Molestiae.</td>
      <td>Rem?</td>
      <td>Enim!</td>
      <td>Maxime?</td>
      <td>Reiciendis!</td>
    </tr>
    <tr>
      <td>Commodi.</td>
      <td>At.</td>
      <td>Earum?</td>
      <td>Fugit.</td>
      <td>Maxime?</td>
    </tr>
    <tr>
      <td>Eligendi?</td>
      <td>Quis.</td>
      <td>Error?</td>
      <td>Atque.</td>
      <td>Perferendis.</td>
    </tr>
    <tr>
      <td>Quidem.</td>
      <td>Odit!</td>
      <td>Tempore.</td>
      <td>Voluptates.</td>
      <td>Facere!</td>
    </tr>
    <tr>
      <td>Repudiandae!</td>
      <td>Accusamus?</td>
      <td>Soluta.</td>
      <td>Incidunt.</td>
      <td>Aliquid?</td>
    </tr>
    <tr>
      <td>Quisquam?</td>
      <td>Eius.</td>
      <td>Obcaecati?</td>
      <td>Maxime.</td>
      <td>Nihil.</td>
    </tr>
    <tr>
      <td>Minus.</td>
      <td>Magni?</td>
      <td>Necessitatibus?</td>
      <td>Asperiores.</td>
      <td>Iure.</td>
    </tr>
    <tr>
      <td>Ipsa!</td>
      <td>Temporibus.</td>
      <td>Non!</td>
      <td>Dolore.</td>
      <td>Veritatis.</td>
    </tr>
    <tr>
      <td>Ea!</td>
      <td>Officia?</td>
      <td>Doloribus?</td>
      <td>Deleniti?</td>
      <td>Dolorem!</td>
    </tr>
    <tr>
      <td>Sequi?</td>
      <td>Molestias!</td>
      <td>Nesciunt.</td>
      <td>Qui.</td>
      <td>Doloribus?</td>
    </tr>
    <tr>
      <td>Id.</td>
      <td>Enim?</td>
      <td>Quam!</td>
      <td>Sunt!</td>
      <td>Consequuntur.</td>
    </tr>
    <tr>
      <td>Reprehenderit?</td>
      <td>Ut?</td>
      <td>Veritatis!</td>
      <td>Corporis!</td>
      <td>Ipsa.</td>
    </tr>
    <tr>
      <td>Blanditiis!</td>
      <td>Veniam!</td>
      <td>Tenetur.</td>
      <td>Eos?</td>
      <td>Repellat!</td>
    </tr>
    <tr>
      <td>Enim?</td>
      <td>Atque!</td>
      <td>Aspernatur?</td>
      <td>Fugit.</td>
      <td>Voluptatibus!</td>
    </tr>
    <tr>
      <td>Nihil.</td>
      <td>Distinctio!</td>
      <td>Aut!</td>
      <td>Rerum!</td>
      <td>Dolorem?</td>
    </tr>
    <tr>
      <td>Inventore!</td>
      <td>Hic.</td>
      <td>Explicabo.</td>
      <td>Sit.</td>
      <td>A.</td>
    </tr>
    <tr>
      <td>Inventore.</td>
      <td>A.</td>
      <td>Nam.</td>
      <td>Beatae.</td>
      <td>Consequatur.</td>
    </tr>
    <tr>
      <td>Eligendi.</td>
      <td>Illum.</td>
      <td>Enim?</td>
      <td>Dignissimos!</td>
      <td>Ducimus?</td>
    </tr>
    <tr>
      <td>Eligendi!</td>
      <td>Fugiat?</td>
      <td>Deleniti!</td>
      <td>Rerum?</td>
      <td>Delectus?</td>
    </tr>
    <tr>
      <td>Sit.</td>
      <td>Nam.</td>
      <td>Eveniet?</td>
      <td>Veritatis.</td>
      <td>Adipisci!</td>
    </tr>
    <tr>
      <td>Nostrum?</td>
      <td>Totam?</td>
      <td>Voluptates!</td>
      <td>Ab!</td>
      <td>Consequatur.</td>
    </tr>
    <tr>
      <td>Error!</td>
      <td>Dicta?</td>
      <td>Voluptatum?</td>
      <td>Corporis!</td>
      <td>Ea.</td>
    </tr>
    <tr>
      <td>Vel.</td>
      <td>Asperiores.</td>
      <td>Facere.</td>
      <td>Quae.</td>
      <td>Fugiat.</td>
    </tr>
    <tr>
      <td>Libero?</td>
      <td>Molestias.</td>
      <td>Praesentium!</td>
      <td>Accusantium!</td>
      <td>Tenetur.</td>
    </tr>
    <tr>
      <td>Eveniet.</td>
      <td>Quam.</td>
      <td>Quibusdam.</td>
      <td>Eaque?</td>
      <td>Dolore!</td>
    </tr>
    <tr>
      <td>Asperiores.</td>
      <td>Impedit.</td>
      <td>Ullam?</td>
      <td>Quod.</td>
      <td>Placeat.</td>
    </tr>
    <tr>
      <td>In?</td>
      <td>Aliquid.</td>
      <td>Voluptatum!</td>
      <td>Omnis?</td>
      <td>Magni.</td>
    </tr>
    <tr>
      <td>Autem.</td>
      <td>Earum!</td>
      <td>Debitis!</td>
      <td>Eius.</td>
      <td>Incidunt.</td>
    </tr>
    <tr>
      <td>Blanditiis?</td>
      <td>Impedit.</td>
      <td>Libero?</td>
      <td>Reiciendis!</td>
      <td>Tempore.</td>
    </tr>
    <tr>
      <td>Quasi.</td>
      <td>Reiciendis.</td>
      <td>Aut?</td>
      <td>Architecto?</td>
      <td>Vero!</td>
    </tr>
    <tr>
      <td>Fuga!</td>
      <td>Illum!</td>
      <td>Tenetur!</td>
      <td>Vitae.</td>
      <td>Natus.</td>
    </tr>
    <tr>
      <td>Dolorem?</td>
      <td>Eaque!</td>
      <td>Vero?</td>
      <td>Quibusdam.</td>
      <td>Deleniti?</td>
    </tr>
    <tr>
      <td>Minus.</td>
      <td>Accusantium?</td>
      <td>Ab.</td>
      <td>Cupiditate.</td>
      <td>Atque?</td>
    </tr>
    <tr>
      <td>Hic.</td>
      <td>Eligendi.</td>
      <td>Sit?</td>
      <td>Nihil.</td>
      <td>Dolor.</td>
    </tr>
    <tr>
      <td>Quidem.</td>
      <td>In?</td>
      <td>Nesciunt?</td>
      <td>Adipisci.</td>
      <td>Neque.</td>
    </tr>
    <tr>
      <td>Eos.</td>
      <td>Incidunt!</td>
      <td>Quis?</td>
      <td>Quod?</td>
      <td>Vitae!</td>
    </tr>
    <tr>
      <td>Ullam!</td>
      <td>Facilis.</td>
      <td>Tempora!</td>
      <td>Accusantium.</td>
      <td>Consequuntur?</td>
    </tr>
    <tr>
      <td>Numquam?</td>
      <td>At.</td>
      <td>Incidunt.</td>
      <td>Tenetur?</td>
      <td>Voluptatem.</td>
    </tr>
    <tr>
      <td>Iusto?</td>
      <td>Inventore.</td>
      <td>Molestias.</td>
      <td>Accusantium.</td>
      <td>Sunt.</td>
    </tr>
    <tr>
      <td>Repellendus!</td>
      <td>Ex.</td>
      <td>Magnam.</td>
      <td>Odit!</td>
      <td>Iste?</td>
    </tr>
    <tr>
      <td>Id!</td>
      <td>Reiciendis?</td>
      <td>Rem.</td>
      <td>Quae!</td>
      <td>Laborum?</td>
    </tr>
    <tr>
      <td>Exercitationem?</td>
      <td>Maiores.</td>
      <td>Minima.</td>
      <td>Nemo!</td>
      <td>Sequi.</td>
    </tr>
    <tr>
      <td>Qui.</td>
      <td>Impedit?</td>
      <td>Reprehenderit.</td>
      <td>Distinctio.</td>
      <td>Natus?</td>
    </tr>
    <tr>
      <td>Suscipit!</td>
      <td>Tenetur.</td>
      <td>Cumque!</td>
      <td>Molestiae.</td>
      <td>Fugiat?</td>
    </tr>
    <tr>
      <td>Sunt?</td>
      <td>Quis?</td>
      <td>Officia.</td>
      <td>Incidunt.</td>
      <td>Voluptate.</td>
    </tr>
    <tr>
      <td>Possimus.</td>
      <td>Mollitia!</td>
      <td>Eveniet!</td>
      <td>Temporibus.</td>
      <td>Mollitia!</td>
    </tr>
    <tr>
      <td>Incidunt.</td>
      <td>Fugiat.</td>
      <td>Error.</td>
      <td>Odit.</td>
      <td>Cumque?</td>
    </tr>
    <tr>
      <td>Maxime?</td>
      <td>Qui!</td>
      <td>Sapiente!</td>
      <td>Natus.</td>
      <td>Soluta?</td>
    </tr>
  </tbody>
</table>
```

CSS

```Css
body {
  margin: 0;
  padding: 2rem;
}

table {
  text-align: left;
  position: relative;
  border-collapse: collapse; 
}
th, td {
  padding: 0.25rem;
}
tr.red th {
  background: red;
  color: white;
}
tr.green th {
  background: green;
  color: white;
}
tr.purple th {
  background: purple;
  color: white;
}
th {
  background: white;
  position: sticky;
  top: 0; /* Don't forget this, required for the stickiness */
  box-shadow: 0 2px 2px -1px rgba(0, 0, 0, 0.4);
}
```



