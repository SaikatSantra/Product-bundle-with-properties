## Product-bundle-with-properties

```
<select
    id="product-select-{{ product.id }}{{ product-form }}{{ section.id }}{{ block.id }}"
   {% if frame_product %} name="items[][id]" {% else %} name="id" {% endif %}        
    class="{% if product.options.size > 1 %}multi_select{% endif %}"
    data-variants>
    {% for v in product.variants %}
      <option
        {% if v == variant %}
        selected="selected"
        {% endif %}
        value="{{ v.id }}"
        data-featured-image="{{ v.featured_media }}"
        data-image="{{ v.featured_media | product_img_url: '600x' }}"
        data-sku="{{ v.sku }}">{{ v.title }}</option>
    {% endfor %}
  </select>
<input id="frame_for" type="hidden"  name="items[][properties][Frame]" value="{{ frame_product.selected_or_first_available_variant.title }}">
```
#Need to use those things for the items properties 
```
input variant: name="items[][id]"
input quantity: name="items[][quantity]"
input property: name="items[][properties][property_label]"
```

#Need to use product form tag 
```
 <form method="post" action="/cart/add" id="product_form_{{product.id}}" accept-charset="UTF-8" class="shopify-product-form" enctype="multipart/form-data">
    </form>
```

![image](https://github.com/user-attachments/assets/56fb0164-1b36-4383-bd21-d3f2b1a400c7)
![image](https://github.com/user-attachments/assets/af350f56-ff76-4bec-a77f-810f86df544b)
