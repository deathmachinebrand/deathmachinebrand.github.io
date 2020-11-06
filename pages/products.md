---
layout: products
title: Products
permalink: /products
---

{% if site.data.products.size > 0 %}
<table width="100%" class="products">

{% assign counter = 0 %}
{% for product in site.data.products %}

    {% if product.status == 'active'%}
         {% assign counter = counter | plus:1 %}
         {% assign mod = counter | modulo:3 %}
          {% if mod == 1 %} 
             <tr>
           {% endif %} 
                  
            <td>
                <h3>{{ product.title }}</h3>
                  <a href="https://superhappytimedeathmachine.com/products/{{product.handle}}">
                    <img src="{{ product.imageSrc }}" style="width:100" border="0">
                </a>    
                 ${{ product.variantPrice }}
                 <div class="product-desc">
                    {{ product.body}}
                 </div>
           </td>
           
        {% if mod == 0 %} 
        </tr>
        {% endif %}
          
    {% endif %}
{% endfor %}

</table>
{% endif %}