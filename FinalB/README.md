
# Final Project   -  Part B

## We decided to add more data to our model bacause we saw that our data is too similar based on our models results (and with sigal's adivce)

# We switched the 'text' title and the 'type' title in mistake so at the code it seems to be the opposite

## Get recipes from allrecipes site


```python
%matplotlib inline
import matplotlib.pyplot as plt
from matplotlib.pyplot import rcParams
```


```python
import requests
from bs4 import BeautifulSoup
import json

def fix (so):
    return "http://allrecipes.com/"+so.get('href')

r = requests.get("http://allrecipes.com/recipes/1254/desserts/fruit-desserts/apple-desserts/?internalSource=recipe%20breadcrumb&referringId=8358&referringContentType=recipe&referringPosition=5&clickId=recipe%20breadcrumb%205&page=2")
soup = BeautifulSoup(r.text, "lxml")
g=soup.find("section", class_="grid salvattore-grid grid-fixed").find_all("a")

recipe_links = map(fix,g)[0:150]

```


```python
from recipe_scrapers import scrap_me
from collections import Counter
# recipe_links
r1 = [k for k,v in Counter(recipe_links).items() if v>1]
r1
# len(recipe_links)
# for link in recipe_links:
#       print(link)
#     scrap_me = scrap_me(link)
#     scrap_me.instructions()


```




    ['http://allrecipes.com//recipe/15800/apple-betty/',
     'http://allrecipes.com//recipe/232922/apple-cinnamon-white-cake/',
     'http://allrecipes.com//recipe/46395/applesauce-bars/',
     'http://allrecipes.com//recipe/12681/apple-pie-filling/',
     'http://allrecipes.com//recipe/68348/apple-brownies/',
     'http://allrecipes.com//recipe/57582/sour-cream-apple-pie-deluxe/',
     'http://allrecipes.com//recipe/25552/apple-banana-cupcakes/',
     'http://allrecipes.com//recipe/15908/caramel-apple-pie-ii/',
     'http://allrecipes.com//recipe/8358/apple-cake-iv/',
     'http://allrecipes.com//recipe/177053/slow-cooker-apple-crisp/',
     'http://allrecipes.com//recipe/14148/orange-cream-fruit-salad/',
     'http://allrecipes.com//recipe/16853/maple-apple-crisp/',
     'http://allrecipes.com//recipe/229088/apple-crisp-with-oat-topping/',
     'http://allrecipes.com//recipe/24069/nanas-apple-crisp/',
     'http://allrecipes.com//recipe/46232/old-fashioned-apple-dumplings/',
     'http://allrecipes.com//recipe/9768/glazed-apple-cookies/',
     'http://allrecipes.com//recipe/8454/apple-cake-v/',
     'http://allrecipes.com//recipe/22338/apple-crisp-ii/',
     'http://allrecipes.com//recipe/7620/apple-bundt-cake/',
     'http://allrecipes.com//recipe/15138/apple-pecan-cobbler/']




```python
def fix (so):
    return "http://allrecipes.com/"+so.get('href')

r = requests.get("http://allrecipes.com/recipes/17527/desserts/fruit-desserts/banana-desserts/?internalSource=hub%20nav&referringId=17140&referringContentType=recipe%20hub&linkName=hub%20nav%20daughter&clickId=hub%20nav%202&page=2")
soup = BeautifulSoup(r.text, "lxml")
g=soup.find("section", class_="grid salvattore-grid grid-fixed").find_all("a")

recipe_links1 = map(fix,g)[0:150]




```


```python
r2 = [k for k,v in Counter(recipe_links1).items() if v>1]
r2
```




    ['http://allrecipes.com//recipe/15002/banana-oatmeal-cookies-i/',
     'http://allrecipes.com//recipe/21310/aunt-bettys-banana-pudding/',
     'http://allrecipes.com//recipe/25789/banana-bars/',
     'http://allrecipes.com//recipe/20038/campfire-banana-splits/',
     'http://allrecipes.com//recipe/20256/banana-chocolate-chip-dessert/',
     'http://allrecipes.com//recipe/8445/english-trifle/',
     'http://allrecipes.com//recipe/8258/banana-cake-v/',
     'http://allrecipes.com//recipe/12625/banoffee/',
     'http://allrecipes.com//recipe/7899/banana-oatmeal-crumb-cake/',
     'http://allrecipes.com//recipe/17983/banana-oatmeal-cookies-ii/',
     'http://allrecipes.com//recipe/77309/creamy-banana-pudding/',
     'http://allrecipes.com//recipe/11386/banana-bread-cookies/',
     'http://allrecipes.com//recipe/18990/banana-pudding-i/',
     'http://allrecipes.com//recipe/25587/gramma-berthas-banana-cake/',
     'http://allrecipes.com//recipe/8301/banana-loaf-cake-i/',
     'http://allrecipes.com//recipe/24943/chocolate-banana-bread-pudding/',
     'http://allrecipes.com//recipe/16875/homemade-banana-pudding-pie/',
     'http://allrecipes.com//recipe/188361/cocoa-banana-bars/',
     'http://allrecipes.com//recipe/21313/banana-pudding-iii/',
     'http://allrecipes.com//recipe/25559/banana-cake-x/']




```python
def fix (so):
    return "http://allrecipes.com/"+so.get('href')

r = requests.get("http://allrecipes.com/recipes/17532/desserts/fruit-desserts/blueberry-desserts/?internalSource=hub%20nav&referringId=17140&referringContentType=recipe%20hub&linkName=hub%20nav%20daughter&clickId=hub%20nav%202&page=2")
soup = BeautifulSoup(r.text, "lxml")
g=soup.find("section", class_="grid salvattore-grid grid-fixed").find_all("a")

recipe_links2 = map(fix,g)[0:150]
r3 = [k for k,v in Counter(recipe_links2).items() if v>1]
r3

```




    ['http://allrecipes.com//recipe/27478/white-chocolate-blueberry-cheesecake/',
     'http://allrecipes.com//recipe/9651/blueberry-bars/',
     'http://allrecipes.com//recipe/72747/blueberry-lemon-pound-cake/',
     'http://allrecipes.com//recipe/65071/blueberry-ricotta-squares/',
     'http://allrecipes.com//recipe/74029/nova-scotia-blueberry-cream-cake/',
     'http://allrecipes.com//recipe/237063/chef-johns-blueberry-clafoutis/',
     'http://allrecipes.com//recipe/64787/cherry-blueberry-pie/',
     'http://allrecipes.com//recipe/22194/blueberry-coffee-cake-ii/',
     'http://allrecipes.com//recipe/9652/blueberry-drop-cookies/',
     'http://allrecipes.com//recipe/7934/blueberry-cheesecake/',
     'http://allrecipes.com//recipe/12341/blueberry-cherry-pie/',
     'http://allrecipes.com//recipe/12657/topless-blueberry-pie/',
     'http://allrecipes.com//recipe/228532/blueberry-shortbread-bars/',
     'http://allrecipes.com//recipe/77297/blueberry-streusel-cobbler/',
     'http://allrecipes.com//recipe/12395/fresh-blueberry-pie-ii/',
     'http://allrecipes.com//recipe/25028/blueberry-lemon-crumb-bars/',
     'http://allrecipes.com//recipe/223253/easy-blueberry-cobbler/',
     'http://allrecipes.com//recipe/74837/sugar-free-blueberry-coffee-cake/',
     'http://allrecipes.com//cook/foodwisheswithchefjohn/',
     'http://allrecipes.com//recipe/60012/blueberry-gingerbread/',
     'http://allrecipes.com//recipe/223399/best-blueberry-buckle/']




```python
final_links_recipe = r1 + r2 + r3
final_links_recipe
```




    ['http://allrecipes.com//recipe/15800/apple-betty/',
     'http://allrecipes.com//recipe/232922/apple-cinnamon-white-cake/',
     'http://allrecipes.com//recipe/46395/applesauce-bars/',
     'http://allrecipes.com//recipe/12681/apple-pie-filling/',
     'http://allrecipes.com//recipe/68348/apple-brownies/',
     'http://allrecipes.com//recipe/57582/sour-cream-apple-pie-deluxe/',
     'http://allrecipes.com//recipe/25552/apple-banana-cupcakes/',
     'http://allrecipes.com//recipe/15908/caramel-apple-pie-ii/',
     'http://allrecipes.com//recipe/8358/apple-cake-iv/',
     'http://allrecipes.com//recipe/177053/slow-cooker-apple-crisp/',
     'http://allrecipes.com//recipe/14148/orange-cream-fruit-salad/',
     'http://allrecipes.com//recipe/16853/maple-apple-crisp/',
     'http://allrecipes.com//recipe/229088/apple-crisp-with-oat-topping/',
     'http://allrecipes.com//recipe/24069/nanas-apple-crisp/',
     'http://allrecipes.com//recipe/46232/old-fashioned-apple-dumplings/',
     'http://allrecipes.com//recipe/9768/glazed-apple-cookies/',
     'http://allrecipes.com//recipe/8454/apple-cake-v/',
     'http://allrecipes.com//recipe/22338/apple-crisp-ii/',
     'http://allrecipes.com//recipe/7620/apple-bundt-cake/',
     'http://allrecipes.com//recipe/15138/apple-pecan-cobbler/',
     'http://allrecipes.com//recipe/15002/banana-oatmeal-cookies-i/',
     'http://allrecipes.com//recipe/21310/aunt-bettys-banana-pudding/',
     'http://allrecipes.com//recipe/25789/banana-bars/',
     'http://allrecipes.com//recipe/20038/campfire-banana-splits/',
     'http://allrecipes.com//recipe/20256/banana-chocolate-chip-dessert/',
     'http://allrecipes.com//recipe/8445/english-trifle/',
     'http://allrecipes.com//recipe/8258/banana-cake-v/',
     'http://allrecipes.com//recipe/12625/banoffee/',
     'http://allrecipes.com//recipe/7899/banana-oatmeal-crumb-cake/',
     'http://allrecipes.com//recipe/17983/banana-oatmeal-cookies-ii/',
     'http://allrecipes.com//recipe/77309/creamy-banana-pudding/',
     'http://allrecipes.com//recipe/11386/banana-bread-cookies/',
     'http://allrecipes.com//recipe/18990/banana-pudding-i/',
     'http://allrecipes.com//recipe/25587/gramma-berthas-banana-cake/',
     'http://allrecipes.com//recipe/8301/banana-loaf-cake-i/',
     'http://allrecipes.com//recipe/24943/chocolate-banana-bread-pudding/',
     'http://allrecipes.com//recipe/16875/homemade-banana-pudding-pie/',
     'http://allrecipes.com//recipe/188361/cocoa-banana-bars/',
     'http://allrecipes.com//recipe/21313/banana-pudding-iii/',
     'http://allrecipes.com//recipe/25559/banana-cake-x/',
     'http://allrecipes.com//recipe/27478/white-chocolate-blueberry-cheesecake/',
     'http://allrecipes.com//recipe/9651/blueberry-bars/',
     'http://allrecipes.com//recipe/72747/blueberry-lemon-pound-cake/',
     'http://allrecipes.com//recipe/65071/blueberry-ricotta-squares/',
     'http://allrecipes.com//recipe/74029/nova-scotia-blueberry-cream-cake/',
     'http://allrecipes.com//recipe/237063/chef-johns-blueberry-clafoutis/',
     'http://allrecipes.com//recipe/64787/cherry-blueberry-pie/',
     'http://allrecipes.com//recipe/22194/blueberry-coffee-cake-ii/',
     'http://allrecipes.com//recipe/9652/blueberry-drop-cookies/',
     'http://allrecipes.com//recipe/7934/blueberry-cheesecake/',
     'http://allrecipes.com//recipe/12341/blueberry-cherry-pie/',
     'http://allrecipes.com//recipe/12657/topless-blueberry-pie/',
     'http://allrecipes.com//recipe/228532/blueberry-shortbread-bars/',
     'http://allrecipes.com//recipe/77297/blueberry-streusel-cobbler/',
     'http://allrecipes.com//recipe/12395/fresh-blueberry-pie-ii/',
     'http://allrecipes.com//recipe/25028/blueberry-lemon-crumb-bars/',
     'http://allrecipes.com//recipe/223253/easy-blueberry-cobbler/',
     'http://allrecipes.com//recipe/74837/sugar-free-blueberry-coffee-cake/',
     'http://allrecipes.com//cook/foodwisheswithchefjohn/',
     'http://allrecipes.com//recipe/60012/blueberry-gingerbread/',
     'http://allrecipes.com//recipe/223399/best-blueberry-buckle/']




```python
import unicodedata
import time
from recipe_scrapers import scrap_me
# scrap_me = scrap_me("http://allrecipes.com//recipe/232922/apple-cinnamon-white-cake/")
# print(scrap_me.instructions())
new_data=[]
for link in final_links_recipe:
#            print('"' + link + '"')
#          print(st)
        scrap_me1 = scrap_me(link)
        recipe = scrap_me1.instructions()
        new_data.append(recipe)

new_data
```




    [[u'Preheat oven to 375 degrees F (190 degrees C). Lightly grease a 9 inch pie plate.',
      u'Mound sliced apples in the pie plate. Sprinkle with orange juice.',
      u'In a medium bowl, mix the flour, sugar, cinnamon, nutmeg, and salt. Cut in butter until the mixture resembles coarse crumbs. Scatter over the apples.',
      u'Bake in preheated oven for 45 minutes. Serve warm.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Grease and flour a 9x5-inch loaf pan.',
      u'Mix brown sugar and cinnamon together in a bowl.',
      u'Beat white sugar and butter together in a bowl using an electric mixer until smooth and creamy. Beat in eggs, 1 at a time, until incorporated; add vanilla extract.',
      u'Combine flour and baking powder together in a bowl; stir into creamed butter mixture. Mix milk into batter until smooth. Pour half the batter into the prepared loaf pan; add half the apples and half the brown sugar mixture. Lightly pat apple mixture into batter. Pour the remaining batter over apple layer; top with remaining apples and brown sugar mixture. Lightly pat apples into batter; swirl brown sugar mixture through apples using a finger or spoon.',
      u'Bake in the preheated oven until a toothpick inserted in the center of the loaf comes out clean, 30 to 40 minutes.',
      u''],
     [u'Preheat the oven to 350 degrees F (175 degrees C). Grease a 9x13 inch baking pan.',
      u'In a medium bowl, mix together the butter, brown sugar and egg until smooth. Stir in applesauce. Combine the flour, baking soda, salt and pumpkin pie spice; stir into the applesauce mixture until well blended. Spread evenly into the prepared pan.',
      u'Bake for 25 minutes in the preheated oven, or until edges are golden. Cool in the pan over a wire rack.',
      u"In a small bowl, mix together the confectioners' sugar and margarine. Stir in vanilla and milk until smooth. Spread over cooled bars before cutting into squares.",
      u''],
     [u'In a large bowl, toss apples with lemon juice and set aside. Pour water into a Dutch oven over medium heat. Combine sugar, cornstarch, cinnamon, salt, and nutmeg in a bowl; add to water, stir well, and bring to a boil. Boil for 2 minutes, stirring constantly.',
      u'Add apples and return to a boil. Reduce heat, cover and simmer until apples are tender, about 6 to 8 minutes. Cool for 30 minutes.',
      u'Ladle into 5 freezer containers, leaving 1/2 inch headspace. Cool at room temperature no longer than 1 1/2 hours.',
      u'Seal and freeze. Can be stored for up to 12 months.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Grease a 9x9 inch baking dish.',
      u'In a large bowl, beat together the melted butter, sugar, and egg until fluffy. Fold in the apples and walnuts. In a separate bowl, sift together the flour, salt, baking powder, baking soda, and cinnamon. Stir the flour mixture into the wet mixture until just blended. Spread the batter evenly in the prepared baking dish.',
      u'Bake 35 minutes in the preheated oven, or until a toothpick inserted in the center comes out clean.',
      u''],
     [u'Preheat the oven to 425 degrees F (220 degrees C). Press the pie crust into and up the sides of a 9 inch pie plate.',
      u'In a medium bowl, stir together 3/4 cup sugar, 2 tablespoons of flour, and salt. Mix in the sour cream, egg and vanilla until smooth. Add apples, and stir to coat. Scrape the mixture into the pie shell.',
      u'Bake for 15 minutes in the preheated oven, then reduce heat to 350 degrees F (175 degrees C), and continue baking for 30 minutes more.',
      u'While the pie is baking, prepare the topping in a medium bowl. Stir together 1/3 cup of flour, 1/3 cup sugar, and cinnamon. Cut in the butter until the mixture resembles fine crumbs.',
      u'After the 30 minute bake time has passed, cover the top of the pie with the crumb topping, and continue to bake for 15 minutes, or until topping is lightly browned and apples are tender. Allow the pie to cool, then refrigerate until chilled before serving.',
      u''],
     [u'Preheat oven to 375 degrees F (190 degrees C). Grease and flour 24 muffin cups, or use paper liners. Sift together the flour, baking soda, salt, cinnamon, and nutmeg. Set aside.',
      u'In a large bowl, cream together the shortening and sugar until light and fluffy. Beat in the eggs one at a time, then stir in the vanilla and buttermilk. Beat in the flour mixture, mixing just until incorporated. Fold in the mashed bananas and shredded apples. Fill each muffin cup half full.',
      u'Bake in the preheated oven for 20 to 25 minutes, or until a toothpick inserted into the center comes out clean. Allow to cool.',
      u''],
     [u'Preheat oven to 375 degrees F (190 degrees C).',
      u'To Make Taffy: In a small bowl combine brown sugar, melted butter or margarine, and 1/3 cup flour. Mix well and set aside.',
      u'To Make Apple Filling: Place apples in a large bowl. Add white sugar, 3 tablespoons flour, cinnamon, and lemon juice. Toss until all ingredients are mixed well and apples are thoroughly coated.',
      u'Spoon half of apple filling into pastry-lined deep-dish pan. Top with half of caramels and half of taffy mixture. Repeat process with remaining apple filling, caramels and taffy mixture. Place top pastry over filling and seal well (this is very important--if edges are not sealed, caramel will leak out all over). Cut steam vents and brush top crust with milk or light cream.',
      u'Cover pie with foil and place on a baking sheet. Bake in preheated oven for 25 minutes. Remove foil from pie and bake for another 20 to 25 minutes, until crust is golden. Serve warm.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C) lightly grease and flour a 9x13 inch pan.',
      u'Sift together flour, salt, cinnamon and baking powder. Set aside.',
      u'In a large bowl, beat eggs and sugar for 15 minutes on high speed with an electric mixer. Add oil and blend in.',
      u'Add four mixture and mix well. Add vanilla. Fold in apples and nuts. Pour batter into 9x13 inch pan.',
      u'In a small bowl, mix 4 teaspoons sugar with 1 teaspoon cinnamon. Sprinkle over cake.',
      u'Bake at 350 degrees F (175 degrees C) for 50 to 60 minutes or until a toothpick inserted into center of cake comes out clean.',
      u''],
     [u'Mix flour, brown sugar, 1/2 cup of white sugar, 1/2 teaspoon cinnamon, nutmeg, and salt together in a bowl. Combine butter with the flour mixture using fingers or a fork until coarse crumbs form. Stir in walnuts and set aside.',
      u'Whisk together 1/3 cup sugar, cornstarch, ginger, and 1/2 teaspoon cinnamon. Place the apples in a slow cooker, stir in the cornstarch mixture; toss with lemon juice. Sprinkle the walnut crumb topping on top. Cover and cook on High for 2 hours or Low for 4 hours, until apples are tender. Partially uncover the slow cooker to allow the topping to harden, about 1 hour.',
      u''],
     [u'In a medium mixing bowl, combine pudding mix, milk, and orange juice concentrate. Beat with an electric mixer on medium speed for 2 minutes. Mix in sour cream.',
      u'In a large salad bowl, combine fruits. Gently mix in orange dressing. Cover, and refrigerate for 2 hours.',
      u''],
     [u'Preheat oven to 375 degrees F (190 degrees C).',
      u'Place apples in an 8x8 inch baking dish. Toss apples with syrup. In a separate bowl, mix together flour, oats, sugar, and salt. Cut in butter until mixture is crumbly. Sprinkle mixture evenly over apples.',
      u'Bake in the preheated oven for 35 minutes, until topping is golden brown. Serve warm or at room temperature.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C).',
      u'Toss apples with white sugar and 1/2 teaspoon cinnamon in a medium bowl to coat; pour into a 9-inch square baking dish.',
      u'Mix brown sugar, oats, flour, and 1 teaspoon cinnamon in a separate bowl. Use a pastry cutter or 2 forks to mash cold butter into the oats mixture until the mixture resembles coarse crumbs; spread over the apples to the edges of the baking dish. Pat the topping gently until even.',
      u'Bake in preheated oven until golden brown and sides are bubbling, about 40 minutes.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C).',
      u'Place apples in a 9x13 inch baking dish. In a bowl, mix melted butter, flour, sugar, oats, and 1 tablespoon cinnamon to form a crumbly mixture. Sprinkle over apples. Dot with remaining 1/4 cup butter, and sprinkle with remaining 1 tablespoon cinnamon.',
      u'Bake 50 minutes in the preheated oven, until lightly browned and apples are tender.',
      u''],
     [u'Preheat oven to 400 degrees F (200 degrees C). Butter a 9x13 inch pan.',
      u'On a lightly floured surface, roll pastry into a large rectangle, about 24 by 16 inches. Cut into 6 square pieces. Place an apple on each pastry square with the cored opening facing upward. Cut butter into 8 pieces. Place 1 piece of butter in the opening of each apple; reserve remaining butter for sauce. Divide brown sugar between apples, poking some inside each cored opening and the rest around the base of each apple. Sprinkle cinnamon and nutmeg over the apples.',
      u'With slightly wet fingertips, bring one corner of pastry square up to the top of the apple, then bring the opposite corner to the top and press together. Bring up the two remaining corners, and seal. Slightly pinch the dough at the sides to completely seal in the apple. Repeat with the remaining apples. Place in prepared baking dish.',
      u'In a saucepan, combine water, white sugar, vanilla extract and reserved butter. Place over medium heat, and bring to a boil in a large saucepan. Boil for 5 minutes, or until sugar is dissolved. Carefully pour over dumplings.',
      u'Bake in preheated oven for 50 to 60 minutes. Place each apple dumpling in a dessert bowl, and spoon some sauce over the top.',
      u''],
     [u'Beat shortening and brown sugar together until light and fluffy. Beat in egg and blend thoroughly.',
      u'Stir together flour, baking soda, salt, cinnamon, cloves and nutmeg.',
      u'Stir half the dry ingredients into creamed mixture. Stir in nuts, apple and raisins, then stir in remaining half of dry ingredients and milk. Mix well.',
      u'Drop from tablespoon 1 1/2 inches apart onto lightly greased baking sheet. Bake in a preheated 400 degree oven for 10-12 minutes. Remove cookies to racks and while still warm, spread with glaze.',
      u'To make Glaze: Combine powdered sugar, butter, vanilla and enough cream to make glaze of spreading consistency. Beat until smooth. Spread on warm cookies.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Grease and flour a 9x13-inch pan.',
      u'In a large bowl, sift together flour, sugar, salt, and baking soda. Make a well in the center and add oil, eggs, and vanilla. Mix well (batter will be thick). Fold in chopped apples and nuts. Spread batter into prepared pan.',
      u'Bake in preheated oven until a toothpick inserted into cake comes out clean, 40 to 50 minutes. Glaze while still hot.',
      u'To make the glaze: In a saucepan, combine brown sugar, milk, and butter. Bring to a boil and continue cooking for 2 1/2 minutes, stirring constantly. Pour over cake while still hot.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C).',
      u'In a medium bowl, combine flour, oats, brown sugar, cinnamon and melted butter. Stir until crumbly. Press half the oat mixture into a 9x13 inch baking dish. Cover with sliced apples.',
      u'In a medium saucepan, combine white sugar, cornstarch, water and vanilla. Cook, stirring, until thick and clear, 10 minutes. Pour over apples. Cover apples with remaining crumble mixture.',
      u'Bake in preheated oven 45 minutes, until bubbly and golden.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Grease and flour a 10 inch Bundt or tube pan. In a medium bowl, combine the diced apples, 1 tablespoon white sugar and 1 teaspoon cinnamon; set aside. Sift together the flour, baking powder and salt; set aside.',
      u'In a large bowl, combine 2 cups white sugar, oil, orange juice, vanilla and eggs. Beat at high speed until smooth. Stir in flour mixture. Fold in chopped walnuts.',
      u'Pour 1/3 of the batter into prepared pan. Sprinkle with 1/2 of the apple mixture. Alternate layers of batter and filling, ending with batter.',
      u"Bake in preheated oven for 55 to 60 minutes, or until the top springs back when lightly touched. Let cool in pan for 10 minutes, then turn out onto a wire rack and cool completely. Sprinkle with confectioners' sugar.",
      u''],
     [u'Preheat oven to 325 degrees F (165 degrees C). Generously grease a 2-quart baking dish.',
      u'Arrange apple slices in an even layer in the baking dish. In a small bowl, mix together 1/2 cup sugar, cinnamon, and 1/2 cup pecans. Sprinkle mixture over apples.',
      u'In a medium bowl, mix together flour, 1 cup sugar, baking powder, and salt. In a separate bowl whisk together egg, evaporated milk, and melted butter. Pour milk mixture into flour mixture all at once, and stir until smooth. Pour mixture over apples, and sprinkle top with 1/4 cup pecans.',
      u'Bake in the preheated oven for 55 minutes.',
      u''],
     [u'Preheat oven to 375 degrees F (190 degrees C).',
      u'In a medium bowl, cream butter and sugar together until smooth. Stir in the eggs and vanilla. Sift together the flour, baking soda, cloves and cinnamon, stir into the creamed mixture. Then add the mashed bananas, rolled oats and chocolate chips, mix until well blended.',
      u'Drop dough by rounded spoonfuls onto unprepared cookie sheets. Bake for 10 to 12 minutes in the preheated oven. Remove cookies from pan to cool on wire racks.',
      u''],
     [u'In a medium bowl, combine pudding mix and milk and stir until mix is dissolved. Refrigerate 15 minutes, until partially set.',
      u'Stir condensed milk into pudding mixture until smooth. Fold in sour cream and whipped topping. Fold in bananas.',
      u'Make a single layer of vanilla wafers in the bottom of a 9x13 inch dish. Spread pudding evenly over wafers. Crush remaining wafers and sprinkle on top. Refrigerate until serving.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Grease a 9x13 inch baking pan.',
      u'In a large bowl, cream together the shortening and sugar until smooth. Stir in the milk and 1 teaspoon vanilla. Combine the flour, baking soda and 1/2 teaspoon salt; stir into the sugar mixture. Mix in 1 banana, 1 teaspoon lemon juice and walnuts. Spread evenly into the prepared pan.',
      u'Bake for 25 to 30 minutes in the preheated oven, until a toothpick inserted into the center comes out clean. Let bars cool in the pan on a wire rack.',
      u"To make the frosting: In a medium bowl, mix together the melted butter, 1 teaspoon vanilla, confectioners' sugar, 1/2 banana, 1/2 teaspoon of salt and 1/4 teaspoon lemon juice using an electric mixer. Beat until smooth. Spread over cooled bars and then cut into squares.",
      u''],
     [u'Preheat the grill for high heat.',
      u'Spray 4 sheets of aluminum foil, large enough to wrap bananas, with cooking spray.',
      u'Slice the peel of the banana from stem to bottom, while slicing the banana inside lengthwise. The bananas can be cut into slices instead if you like, (while still in the peel) for easier handling later.',
      u'Carefully open the banana just wide enough to place the chocolate chips and marshmallows inside the peel with the banana. Stuff with as much of the chocolate chips and marshmallows as desired.',
      u'Wrap the bananas with the aluminum foil and place on the grill or directly in the coals of a fire. Leave in long enough to melt the chips and the marshmallows, about 5 minutes. Unwrap bananas, open the peels wide, and eat with a spoon.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Grease and flour a 10x15 inch jelly roll pan.',
      u'In a large bowl, cream butter, white sugar and brown sugar until fluffy. Beat in egg and vanilla. Fold in mashed banana. In a separate bowl, mix flour, baking powder and salt. Fold flour mixture into butter mixture. Stir in chocolate chips. Spread in prepared pan.',
      u'Bake in preheated oven 20 minutes, until set. Cool before cutting into squares.',
      u''],
     [u'Slice strawberries and sprinkle them with sugar. Cut the bananas into slices and toss with orange juice. Combine pudding mix with milk and mix until smooth. Cut the cake into 1 inch cubes.',
      u'Use half of the cake cubes to line the bottom of a large glass bowl. Layer half of the strawberries followed by half of the blueberries, and then half of the bananas. Spread half of the pudding over the fruit. Repeat layers in the same order.',
      u'In a medium bowl, whip the cream to stiff peaks and spread over top of trifle. Garnish with maraschino cherries and slivered almonds.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Grease and flour a 9x9 inch pan.',
      u'In a large bowl, cream butter and sugar until light. Add eggs and beat well. Dissolve soda in the sour cream and add it to the butter mixture. Beat well. Add the mashed bananas and mix in. Add cake flour and mix well. Stir in vanilla extract.',
      u'Pour batter into a 9x9 inch pan and bake at 350 degrees F (175 degrees C) for 45 minutes or until done.',
      u''],
     [u'Mix graham cracker crumbs, sugar, melted butter or margarine, and ginger until well blended . Press mixture into a 9 inch pie plate. Cool in refrigerator.',
      u'In a sauce pan, boil an unopened can of sweetened condensed milk for 3 hours. Monitor the water closely, to make sure there is always water in the pan. Remove can from heat and let cool for 10 to 15 minutes.',
      u'Open can and pour toffee into pie crust. Allow to cool.',
      u'Slice bananas over toffee.',
      u'Whip 2 cups of cream and spoon it on top of bananas. Refrigerate before serving.',
      u''],
     [u'Stir together flour, 1 1/3 cups oats, salt, and baking soda.',
      u'In a large bowl, cream 1/2 cup butter or margarine with 2/3 cup brown sugar. Beat in the eggs, then the bananas and vanilla. Beat the flour mixture into the banana mixture. Turn the batter into a greased and floured 8 inch square pan.',
      u'Mix 3/4 cup oats, 1/3 cup brown sugar, melted butter or margarine, walnuts, and cinnamon together until crumbly. Sprinkle evenly over the top of the batter.',
      u'Bake in preheated oven at 350 degrees F (175 degrees C) for 40 to 45 minutes, or until it tests done. Transfer to a rack to cool.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Grease cookie sheets.',
      u'In a large bowl, cream together shortening and brown sugar. Beat in egg and mashed banana, then stir in vanilla. Combine flour, baking soda, salt, cinnamon, and cloves; stir into the banana mixture. Mix in rolled oats and walnuts. Drop by rounded spoonfuls onto prepared cookie sheets. Leave room for spreading.',
      u'Bake for 8 to 10 minutes in preheated oven. Allow cookies to cool on cookie sheets for 5 minutes before transferring to a wire rack to cool completely.',
      u''],
     [u'In large bowl, combine sweetened condensed milk and water. Add pudding mix; beat until well blended. Chill 5 minutes.',
      u'Fold in whipped cream. Spoon 1 cup pudding mixture into 2 1/2-quart glass serving bowl.',
      u'Top with one-third each of the vanilla wafers, bananas and remaining pudding. Repeat layering twice, ending with pudding mixture. Chill thoroughly. Garnish as desired. Store leftovers covered in refrigerator.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Lightly grease baking sheets.',
      u'In a medium bowl, cream together shortening and white sugar until smooth. Beat in eggs, vanilla extract, and banana. Combine flour, baking soda, and salt; blend thoroughly into the shortening mixture to make a sticky batter. Drop by rounded tablespoons onto the prepared baking sheets.',
      u'Bake 10 to 15 minutes in the preheated oven, or until lightly browned.',
      u"In a medium bowl, blend butter, confectioners' sugar, milk and vanilla extract. Adjust amount of milk as necessary to attain a drizzling consistency. Drizzle over warm cookies.",
      u''],
     [u'In medium saucepan combine sugar, flour, and salt. Add eggs and stir well. Stir in milk, and cook over low heat, stirring constantly. When mixture begins to thicken, remove from heat and continue to stir, cooling slightly. Stir in vanilla and butter until smooth.',
      u'Layer pudding with bananas and vanilla wafers in a serving dish. Chill at least one hour in refrigerator before serving.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Spray a 10 inch Bundt pan with non-stick cooking spray.',
      u'In a large bowl, cream together the butter and sugar until light and fluffy. Beat in the eggs one at a time. Beat in the sliced bananas, sour cream and baking soda. Beat in the flour. Pour batter into prepared pan.',
      u'Bake in the preheated oven for 60 minutes, or until a toothpick inserted into the center of the cake comes out clean. Let cool in pan for 10 minutes, then turn out onto a wire rack and cool completely.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Grease and flour a 5x9-inch loaf pan.',
      u'Mash bananas and add flour, sugar, butter, vanilla, baking powder, baking soda and egg. Mix well. Pour into loaf pan.',
      u'Bake in preheated oven until toothpick inserted into center of cake comes out clean, 50 to 60 minutes.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Grease a 9x5 inch loaf pan.',
      u'In a large mixing bowl, mix eggs, milk, sugar, and vanilla until smooth. Stir in bread, bananas, and chocolate chips, and let rest 5 minutes for bread to soak. Pour into prepared pan.',
      u'Line a roasting pan with a damp kitchen towel. Place loaf pan on towel inside roasting pan, and place roasting pan on oven rack. Fill roasting pan with water to reach halfway up the sides of the loaf pan. Bake in preheated oven for 1 hour, or until a knife inserted in the center comes out clean.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C).',
      u'Line the bottom and sides of a 9-inch pie plate with a layer of alternating vanilla wafer crumbs and banana slices.',
      u'To Make Pudding: In a medium saucepan, combine 1 1/2 cups sugar with flour. Mix well, then stir in half the milk. Beat egg yolks and whisk into sugar mixture. Add remaining milk and butter or margarine.',
      u'Place mixture over low heat and cook until thickened, stirring frequently. Remove from heat and stir in vanilla extract. Pour half of pudding over vanilla wafer and banana layer while still hot.',
      u'Make another layer of alternating vanilla wafers and banana slices on top of pudding layer. Pour remaining pudding over second wafer and banana layer.',
      u'To Make Meringue: In a large glass or metal bowl, beat egg whites until foamy. Gradually add 1/4 cup sugar, continuing to beat until whites are stiff. Spread meringue into pie pan, making sure to completely cover pudding layer.',
      u'Bake in preheated oven for 15 minutes, just until meringue is browned. Chill before serving.',
      u''],
     [u'Preheat an oven to 350 degrees F (175 degrees C). Grease a 9x13 inch baking pan.',
      u'Beat the butter and sugar with an electric mixer in a large bowl until light and fluffy. Add the egg and the vanilla and beat until well combined. Stir in the mashed banana, set aside.',
      u'Stir together the flour, baking soda, baking powder, and salt in a separate large bowl, and make a well in the center. Pour the banana mixture into the well and stir just until combined.',
      u'Remove half of the batter from the bowl. Mix the cocoa powder into the batter remaining in the bowl and stir well. Spread the cocoa batter in the bottom of the prepared pan. Spoon the remaining batter on top and use a knife to swirl the batter into a marbled design.',
      u'Bake in the preheated oven until the edges are golden, about 25 minutes. Allow to cool before cutting into 24 pieces.',
      u''],
     [u'In a medium bowl, stir together condensed milk and water. Beat in pudding mix until smooth. Chill in refrigerator 5 minutes.',
      u'In a separate bowl, whip cream until stiff peaks form. Fold whipped cream into chilled pudding mixture.',
      u'Dip sliced bananas in lemon juice. Shake off excess.',
      u'In a 2 1/2 quart serving bowl, spoon 1 cup pudding mixture. Top with one-third each of the wafers, bananas and remaining pudding. Repeat layers twice. Chill until serving.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Grease and flour a 9x13 inch pan. Put 1 tablespoon lemon juice in a measuring cup with 2/3 cup milk. Set aside. Mash bananas with a fork, adding the remaining 1 tablespoon lemon juice to them as you mash. Set aside.',
      u'In a large bowl, combine cake mix and baking soda. Stir to combine. Add bananas, softened butter, milk mixture, eggs and vanilla. Beat at low speed until moistened (about 30 seconds). Beat at medium speed for 4 minutes. Pour into prepared pan.',
      u'Bake in the preheated oven for 30 to 35 minutes, or until center of cake springs back when lightly tapped. A toothpick stuck in the center may leave a slight crumb. Allow to cool on a wire rack.',
      u''],
     [u'Preheat oven to 275 degrees F (135 degrees C). Make the crust: In a food processor, blend together the graham cracker crumbs, almonds and sugar until the almonds are ground fine. Pour in the melted butter and caramel while processing, until mixture is combined. Press the mixture onto the bottom, and half way up the side of a 10 inch springform pan.',
      u'Make the filling: In a metal bowl over a pan of barely simmering water, melt the white chocolate, stirring until smooth. Remove from heat and set aside. In a large bowl, beat the cream cheese and 3/4 cup sugar until smooth. Beat in the eggs and the egg yolks, one at a time. Beat in the flour and the vanilla and blend in the melted white chocolate slowly, beating until the filling is well combined. Pour filling into crust.',
      u'Bake in the middle of preheated oven for 1 hour. Then turn off the heat, and crack the oven door an inch, letting the cheesecake cool in the oven to room temperature. Cover loosely and refrigerate overnight before removing from pan.',
      u'Make the topping: In a saucepan, combine 1/2 cup sugar and cornstarch. Stir in water and blueberries. Bring to a boil, then simmer for 10 minutes, stirring occasionally. Press through a fine sieve. Stir in lemon juice, allow to cool, and store in a glass jar.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Grease a 9 inch square baking dish.',
      u'To make the crust: Cream shortening, sugar, one egg, milk and almond extract in a large bowl. Mix in flour and baking powder, stirring constantly. Spread crust evenly in baking pan. Top with blueberries.',
      u'To make the topping: In a medium bowl, beat two eggs, and cream cheese until smooth. Stir in powdered sugar and almond extract. Spread over blueberries.',
      u'Bake 55 to 60 minutes, or until firm to the touch. Cool in pan before cutting.',
      u''],
     [u'Preheat the oven to 350 degrees F (175 degrees C). Grease and flour a 10 inch Bundt pan.',
      u'In a large bowl, cream together the butter and sugar until light and fluffy. Beat in the eggs one at a time, then stir in the lemon extract. Combine the flour, baking powder, and lemon zest; stir into the batter alternating with the milk. I like to use a spatula and stir by hand, mixing just until blended so the batter is not over mixed. Be sure to scrape the bottom and sides of the bowl often. Fold in the blueberries. Spoon the batter into the prepared pan.',
      u'Bake for 1 hour in the preheated oven, or until a toothpick inserted into the center comes out clean. Let cool in the pan for at least 10 minutes, then invert onto a wire rack to cool completely.',
      u''],
     [u'Preheat the oven to 350 degrees F (175 degrees C). Grease a 9 inch square baking dish.',
      u'In a large bowl, stir together the flour, 3/4 cup of sugar, and baking powder. Add the milk, shortening, 1 egg, and lemon extract, and use an electric mixer to mix on low speed for 1 minute, then on medium speed for 1 minute. Pour the batter into the prepared pan, and spread evenly. Sprinkle blueberries over the batter.',
      u'In a medium bowl, stir together 2 beaten eggs, ricotta cheese, 1/3 cup of sugar, and vanilla extract. Spoon this mixture over the blueberries, and spread evenly.',
      u'Bake for 55 to 60 minutes in the preheated oven, until a knife inserted near the center comes out clean. Cool completely before cutting into squares and serving.',
      u''],
     [u'Preheat the oven to 375 degrees F (190 degrees C). Grease a 9 inch springform pan.',
      u'In a medium bowl, stir together the flour, 1/2 cup of sugar, and baking powder. Mix in the butter by pinching between your fingers or using a pastry blender until the mixture resembles coarse crumbs. Stir in the egg and 1 teaspoon of vanilla. Pat lightly into the bottom of the prepared pan. Pour blueberries over the top.',
      u'In another medium bowl, whisk together the sour cream, 1/2 cup of sugar, egg yolks and 1 teaspoon of vanilla until smooth. Pour over the blueberries.',
      u'Bake for 60 to 70 minutes in the preheated oven, until the top is lightly browned. Cool, then run a knife around the edge of the pan. Remove the outer ring of the pan, and cut into wedges to serve.',
      u''],
     [u'Preheat oven to 425 degrees F (220 degrees C). Generously butter a 2 1/2-quart baking dish.',
      u'Pour blueberries into prepared baking dish.',
      u'Blend milk, sugar, flour, eggs, vanilla extract, and salt in a blender until batter is smooth. Pour batter over blueberries and gently shake to remove any air bubbles.',
      u'Bake in the preheated oven until puffed and center is set, 25 to 30 minutes. Cool until clafoutis deflates and is just warm.',
      u''],
     [u'Preheat the oven to 425 degrees F (220 degrees C).',
      u'Press one of the pie crusts into a 9 inch pie plate. In a large bowl, stir together 1/2 cup of sugar, cornstarch and cinnamon. Stir in the cherry pie filling and blueberries. Spoon into the pie crust. Top with the second crust, and press the edges to seal. Flute edges, or press with the tines of a fork. In a cup, whisk together the egg white and water with a fork. Brush over the top of the pie, then sprinkle with 2 teaspoons of sugar.',
      u'Bake for 45 to 55 minutes in the preheated oven, or until crust is golden brown. Cover the edges of the crust with aluminum foil if they appear to be getting too dark. Cool for at least 2 hours to allow the filling to set before serving.',
      u''],
     [u'Preheat oven to 375 degrees F (190 degrees C). Grease and flour a 9 inch pan. Sift together the flour, baking powder and salt. Set aside.',
      u'In a large bowl, whisk together the oil, sugar and egg. Stir in the flour mixture alternately with the milk, mixing just until incorporated. Fold in the blueberries. Pour batter into prepared pan. Cover with streusel topping.',
      u'For the topping: In a bowl, combine 1/3 cup flour, cinnamon and 1/2 cup sugar. Cut in the butter until mixture resembles coarse crumbs.',
      u'Bake in the preheated oven for 45 minutes, or until a toothpick inserted into the center of the cake comes out clean. Allow to cool.',
      u''],
     [u'In a large mixing bowl, cream the shortening, sugar, egg, milk, almond extract and lemon zest. Mix well after the addition of each ingredient. Combine the flour, baking powder and salt; blend into the sugar mixture. Fold in the blueberries. Cover and chill for 4 hours.',
      u'Preheat oven to 375 degrees F. Drop dough by teaspoonfuls onto ungreased cookie sheets, about 1 1/2 inches apart.',
      u'Bake 12 to 15 minutes in the preheated oven. Let the cookies cool on the baking sheets for a few minutes before transferring to wire racks to cool completely.',
      u''],
     [u'Combine crumbs, 2 tablespoons sugar and butter. Pat mixture into the bottom of a 9 inch springform pan.',
      u'Mash cream cheese until soft and creamy. Gradually beat in sour cream, 3/4 cup sugar, vanilla and flour. Beat in eggs one at a time.',
      u'Pour mixture into crumb-lined pan. Bake in a preheated 325 degree F (165 degrees C) oven for 1 hour or until firm to the touch.',
      u'Cool and then remove cake from pan by loosening edges with a knife. Place frozen blueberries on top of cake. Melt jelly and spoon over blueberries to glaze. Chill until ready to serve.',
      u''],
     [u'Mix sugar, flour, and cinnamon in large bowl. Add fruit. Add lemon juice, and stir well.',
      u'Pour into a 9 inch unbaked pie shell. Dot with the butter or margarine. Cover with top crust and flute edges. Cut small slits in the top.',
      u'Bake at 375 degrees F (190 degrees C) for 1 hour. I put a baking sheet under mine to catch any liquid that might bubble over.',
      u''],
     [u'In a saucepan, combine sugar, cornstarch and salt. Stir in water and 1 cup of blueberries. Cook and stir over medium heat, until thick, approximately 8 to 10 minutes.',
      u'Add butter and let cool about 5 minutes. Stir in remaining blueberries.',
      u'Pour into baked pie shell and cool in the refrigerator for 2 to 4 hours.',
      u''],
     [u'Preheat oven to 375 degrees F (190 degrees C). Place butter cubes in the freezer for 15 minutes.',
      u'Whisk together flour, sugar, salt, and baking powder in a large bowl. Sprinkle in Chinese five-spice powder.',
      u'Cut in frozen butter using a pastry cutter until the butter pieces are about the size of peas. Mix in egg yolk and continue cutting in until thoroughly combined. Drizzle in ice water and stir to combine. The dough should just come together when pinched between your fingers.',
      u'Pour about 3/4 of the crumb mixture into an ungreased 9x9-inch baking dish. Press the mixture down firmly using the back of a spoon. Spread blueberries in one layer and sprinkle with remaining crumbly dough.',
      u'Bake in the preheated oven until the top is golden and sides are crisp and browned, 30 to 35 minutes. Cool completely before serving.',
      u''],
     [u'Preheat oven to 325 degrees F. In bowl, combine blueberries, sweetened condensed milk and lemon peel.',
      u'In large bowl, cut 3/4 cup butter into 1 1/2 cups biscuit mix until crumbly; stir in blueberry mixture. Spread in greased 9-inch square baking pan.',
      u'In small bowl, combine remaining 1/2 cup biscuit mix and brown sugar; cut in remaining 2 tablespoons butter until crumbly. Add nuts. Sprinkle over cobbler.',
      u'Bake 65 to 70 minutes. Serve warm with vanilla ice cream and Blueberry Sauce. Store leftovers covered in refrigerator.',
      u'Blueberry Sauce: In saucepan, combine sugar, cornstarch, cinnamon, and nutmeg. Gradually add water. Cook and stir until thickened. Stir in blueberries; cook and stir until hot.',
      u''],
     [u'Pour one pint of the blueberries into the baked pie shell.',
      u'Combine flour, butter, lemon juice and sugar. Mix thoroughly. Add the remaining pint of blueberries and bring just to a boil over medium heat. Berries should begin to pop open.',
      u'Pour cooked berries over fresh berries. Chill pie and serve with whipped cream.',
      u''],
     [u'Preheat oven to 400 degrees F (200 degrees C). Grease a 9x13 inch baking pan.',
      u'Start by making the crust. In a medium bowl, stir together the 2 cups flour, 2 tablespoons white sugar, lemon zest and salt. Cut in the 1/2 cup butter until the mixture resembles coarse crumbs. Beat egg and vanilla together; stir into the crumb mixture until a dough forms. Press into the bottom of the prepared pan.',
      u'Bake for 12 to 15 minutes in the preheated oven, until golden. Remove from oven and set aside to cool slightly.',
      u'Sprinkle blueberries over the crust. Combine the 1/4 cup sugar and nutmeg; sprinkle over the blueberries. Make the topping: In a medium bowl, cream together the 5 tablespoons butter and brown sugar until smooth. Mix in the flour, so that the mixture is crumbly like streusel. Sprinkle over the blueberry layer.',
      u"Bake for 20 to 25 minutes in the preheated oven, until browned. Cool and then dust with confectioners' sugar before cutting into bars.",
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Place butter in an 8-inch square baking dish.',
      u'Melt butter in the preheating oven, about 5 minutes. Remove from oven.',
      u'Mix flour, sugar, and milk in a bowl until combined; pour batter over melted butter. Scatter blueberries over batter.',
      u'Bake in preheated oven until a toothpick inserted into the center comes out clean, about 1 hour.',
      u''],
     [u'Preheat the oven to 350 degrees F (175 degrees C). Grease and flour a 9x13 inch baking pan.',
      u'In a large bowl, stir together the melted butter, milk, eggs, vanilla and 1 1/2 cups sugar substitute. Combine 3 cups of flour and baking powder; stir into the wet ingredients until just blended. Fold in the blueberries. Spread evenly in the prepared pan.',
      u'In a small bowl, stir together the brown sugar substitute, 3/4 cup of flour, and cinnamon. Stir in the softened butter with a fork until the mixture is crumbly. Sprinkle over the top of the cake.',
      u'Bake for 35 to 40 minutes in the preheated oven, until a toothpick inserted into the center of the cake comes out clean. This cake is best served warm.',
      u''],
     [],
     [u'Preheat the oven to 350 degrees F (175 degrees C). Grease and flour an 11x7 inch baking dish.',
      u'In a large bowl, mix together the oil, 1 cup sugar and molasses until well blended. Beat in the egg. In a separate bowl, stir together the flour, cinnamon, nutmeg, ginger, baking soda and salt. Remove 2 tablespoons of the flour mixture, and toss with blueberries to coat. Stir the remaining dry mixture into the wet ingredients alternately with the buttermilk, mixing after each addition. Carefully stir in blueberries. Pour the batter into the prepared pan, and sprinkle remaining white sugar over the top.',
      u'Bake for 35 to 40 minutes in the preheated oven, until a toothpick inserted into the center comes out clean.',
      u''],
     [u'Preheat oven to 350 degrees F (175 degrees C). Butter and flour a springform pan.',
      u'Sift 2 cups flour, baking powder, and salt into a bowl.',
      u'Beat 1/4 cup butter, 3/4 cup sugar, and egg with an electric mixer in a large bowl until smooth. Gradually add milk and beat until fluffy; stir in flour mixture, making a stiff batter. Gently fold in blueberries and spread batter into prepared springform pan.',
      u'Mix 1/2 cup sugar, 1/3 cup flour, cinnamon, and 1/4 cup butter in a bowl until blended and crumbly in texture. Sprinkle on top of batter, then lightly press topping into batter using fingertips.',
      u'Bake in preheated oven until golden and a toothpick inserted in the middle comes out with moist crumbs, about 40 minutes.',
      u'']]



## Define the cleaning function


```python
# Import BeautifulSoup into your workspace
import re
import nltk
from bs4 import BeautifulSoup 
from nltk.corpus import stopwords # Import the stop word list
def review_to_words( raw_review ): 
    soup_article = BeautifulSoup(raw_review, "html.parser") 
 
    # Use regular expressions to do a find-and-replace
    cleanedSoup_article = re.sub("[^a-zA-Z]",   # The pattern to search for: in this case- all characters but english letters
                          " ",                   # The pattern to replace it with
                          soup_article.get_text() )  # The text to search
   
    lower_case = cleanedSoup_article.lower() # Convert to lower case 
    words = nltk.word_tokenize(lower_case) # Split into words
    words = [w for w in words if not w in stopwords.words("english")]
    porter = nltk.PorterStemmer()
    lancaster = nltk.LancasterStemmer()
    [porter.stem(w) for w in words]
    return ( " ".join( words ))
```


```python
import pandas as pd
columns = ['text' , 'type']
#  df.append(df2, ignore_index=True)
data_pair = [()]
for value in new_data:
    data_pair.append(('recipe',( " ".join( value ))))
df_recipe = pd.DataFrame(data=data_pair, columns=['text','type'])    
# df_recipe

```


```python
df_recipe = df_recipe.ix[1:58]

```

## Add The data to our previous data


```python
import pickle
import unicodedata
df = pd.read_csv('data.csv',header=0, 
                    delimiter=",")
df = df.ix[1:]
df = df.append(df_recipe,ignore_index=True)
df
# df
# pd.DataFrame([[1, 2], [3, 4]], columns=list('AB'))
# df2 = pd.DataFrame([[5, 6], [7, 8]], columns=list('AB'))
# df.append(df2)
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>text</th>
      <th>type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>wiki</td>
      <td>love song flo twenty second single rhythm zone...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>wiki</td>
      <td>season nd season competitive football rangers</td>
    </tr>
    <tr>
      <th>2</th>
      <td>wiki</td>
      <td>afromarengo plana jumping spider species genus...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>wiki</td>
      <td>grisana genus moths noctuidae family</td>
    </tr>
    <tr>
      <th>4</th>
      <td>wiki</td>
      <td>kshatriya kulavatauns title nobility conferred...</td>
    </tr>
    <tr>
      <th>5</th>
      <td>wiki</td>
      <td>robert sands estate historic home located rhin...</td>
    </tr>
    <tr>
      <th>6</th>
      <td>wiki</td>
      <td>cowboy ninja viking image comics comic book cr...</td>
    </tr>
    <tr>
      <th>7</th>
      <td>wiki</td>
      <td>das kriminalmuseum german television series ra...</td>
    </tr>
    <tr>
      <th>8</th>
      <td>wiki</td>
      <td>universal music latin entertainment division u...</td>
    </tr>
    <tr>
      <th>9</th>
      <td>wiki</td>
      <td>molineux stadium mlnju mol new championship fo...</td>
    </tr>
    <tr>
      <th>10</th>
      <td>wiki</td>
      <td>americo sebastiano costantino born october ita...</td>
    </tr>
    <tr>
      <th>11</th>
      <td>wiki</td>
      <td>lance edward lem massey september june native ...</td>
    </tr>
    <tr>
      <th>12</th>
      <td>wiki</td>
      <td>neaspilota genus tephritid fruit flies family ...</td>
    </tr>
    <tr>
      <th>13</th>
      <td>wiki</td>
      <td>faulknor family english family northamptonshir...</td>
    </tr>
    <tr>
      <th>14</th>
      <td>wiki</td>
      <td>stefan dimle born june koping sweden bassplaye...</td>
    </tr>
    <tr>
      <th>15</th>
      <td>wiki</td>
      <td>holzdorf village municipality jessen elster di...</td>
    </tr>
    <tr>
      <th>16</th>
      <td>wiki</td>
      <td>tredinnick cornish surname derives one places ...</td>
    </tr>
    <tr>
      <th>17</th>
      <td>wiki</td>
      <td>scottish cup th season scotland prestigious fo...</td>
    </tr>
    <tr>
      <th>18</th>
      <td>wiki</td>
      <td>gunther schmidt rudersdorf near berlin german ...</td>
    </tr>
    <tr>
      <th>19</th>
      <td>wiki</td>
      <td>robert sargent electrical engineer defense dep...</td>
    </tr>
    <tr>
      <th>20</th>
      <td>wiki</td>
      <td>broken rites formally broken rites australia c...</td>
    </tr>
    <tr>
      <th>21</th>
      <td>wiki</td>
      <td>deep six song american rock band marilyn manso...</td>
    </tr>
    <tr>
      <th>22</th>
      <td>wiki</td>
      <td>usa also known gps iir gps svn american naviga...</td>
    </tr>
    <tr>
      <th>23</th>
      <td>wiki</td>
      <td>luan county station chinese chinese railway st...</td>
    </tr>
    <tr>
      <th>24</th>
      <td>wiki</td>
      <td>stanek stank village administrative district g...</td>
    </tr>
    <tr>
      <th>25</th>
      <td>wiki</td>
      <td>carlo pezzati october italian politician mayor...</td>
    </tr>
    <tr>
      <th>26</th>
      <td>wiki</td>
      <td>john william moore june december u representat...</td>
    </tr>
    <tr>
      <th>27</th>
      <td>wiki</td>
      <td>th division spanish division division spanish ...</td>
    </tr>
    <tr>
      <th>28</th>
      <td>wiki</td>
      <td>pelham range small mountain range southern van...</td>
    </tr>
    <tr>
      <th>29</th>
      <td>wiki</td>
      <td>katzenthal commune haut rhin department grand ...</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>128</th>
      <td>recipe</td>
      <td>Stir together flour, 1 1/3 cups oats, salt, an...</td>
    </tr>
    <tr>
      <th>129</th>
      <td>recipe</td>
      <td>Preheat oven to 350 degrees F (175 degrees C)....</td>
    </tr>
    <tr>
      <th>130</th>
      <td>recipe</td>
      <td>In large bowl, combine sweetened condensed mil...</td>
    </tr>
    <tr>
      <th>131</th>
      <td>recipe</td>
      <td>Preheat oven to 350 degrees F (175 degrees C)....</td>
    </tr>
    <tr>
      <th>132</th>
      <td>recipe</td>
      <td>In medium saucepan combine sugar, flour, and s...</td>
    </tr>
    <tr>
      <th>133</th>
      <td>recipe</td>
      <td>Preheat oven to 350 degrees F (175 degrees C)....</td>
    </tr>
    <tr>
      <th>134</th>
      <td>recipe</td>
      <td>Preheat oven to 350 degrees F (175 degrees C)....</td>
    </tr>
    <tr>
      <th>135</th>
      <td>recipe</td>
      <td>Preheat oven to 350 degrees F (175 degrees C)....</td>
    </tr>
    <tr>
      <th>136</th>
      <td>recipe</td>
      <td>Preheat oven to 350 degrees F (175 degrees C)....</td>
    </tr>
    <tr>
      <th>137</th>
      <td>recipe</td>
      <td>Preheat an oven to 350 degrees F (175 degrees ...</td>
    </tr>
    <tr>
      <th>138</th>
      <td>recipe</td>
      <td>In a medium bowl, stir together condensed milk...</td>
    </tr>
    <tr>
      <th>139</th>
      <td>recipe</td>
      <td>Preheat oven to 350 degrees F (175 degrees C)....</td>
    </tr>
    <tr>
      <th>140</th>
      <td>recipe</td>
      <td>Preheat oven to 275 degrees F (135 degrees C)....</td>
    </tr>
    <tr>
      <th>141</th>
      <td>recipe</td>
      <td>Preheat oven to 350 degrees F (175 degrees C)....</td>
    </tr>
    <tr>
      <th>142</th>
      <td>recipe</td>
      <td>Preheat the oven to 350 degrees F (175 degrees...</td>
    </tr>
    <tr>
      <th>143</th>
      <td>recipe</td>
      <td>Preheat the oven to 350 degrees F (175 degrees...</td>
    </tr>
    <tr>
      <th>144</th>
      <td>recipe</td>
      <td>Preheat the oven to 375 degrees F (190 degrees...</td>
    </tr>
    <tr>
      <th>145</th>
      <td>recipe</td>
      <td>Preheat oven to 425 degrees F (220 degrees C)....</td>
    </tr>
    <tr>
      <th>146</th>
      <td>recipe</td>
      <td>Preheat the oven to 425 degrees F (220 degrees...</td>
    </tr>
    <tr>
      <th>147</th>
      <td>recipe</td>
      <td>Preheat oven to 375 degrees F (190 degrees C)....</td>
    </tr>
    <tr>
      <th>148</th>
      <td>recipe</td>
      <td>In a large mixing bowl, cream the shortening, ...</td>
    </tr>
    <tr>
      <th>149</th>
      <td>recipe</td>
      <td>Combine crumbs, 2 tablespoons sugar and butter...</td>
    </tr>
    <tr>
      <th>150</th>
      <td>recipe</td>
      <td>Mix sugar, flour, and cinnamon in large bowl. ...</td>
    </tr>
    <tr>
      <th>151</th>
      <td>recipe</td>
      <td>In a saucepan, combine sugar, cornstarch and s...</td>
    </tr>
    <tr>
      <th>152</th>
      <td>recipe</td>
      <td>Preheat oven to 375 degrees F (190 degrees C)....</td>
    </tr>
    <tr>
      <th>153</th>
      <td>recipe</td>
      <td>Preheat oven to 325 degrees F. In bowl, combin...</td>
    </tr>
    <tr>
      <th>154</th>
      <td>recipe</td>
      <td>Pour one pint of the blueberries into the bake...</td>
    </tr>
    <tr>
      <th>155</th>
      <td>recipe</td>
      <td>Preheat oven to 400 degrees F (200 degrees C)....</td>
    </tr>
    <tr>
      <th>156</th>
      <td>recipe</td>
      <td>Preheat oven to 350 degrees F (175 degrees C)....</td>
    </tr>
    <tr>
      <th>157</th>
      <td>recipe</td>
      <td>Preheat the oven to 350 degrees F (175 degrees...</td>
    </tr>
  </tbody>
</table>
<p>158 rows × 2 columns</p>
</div>



## Add the new data to the old file


```python
# df = pd.DataFrame(data=df, columns=['text','type'])
# df.to_csv("data_final.csv",index = False)
```

## Cleaning the data


```python
# df.to_csv("data2.csv",index = False)
clean_review = review_to_words( df["type"][156] )
print(clean_review)
```

    preheat oven degrees f degrees c place butter inch square baking dish melt butter preheating oven minutes remove oven mix flour sugar milk bowl combined pour batter melted butter scatter blueberries batter bake preheated oven toothpick inserted center comes clean hour



```python
clean_train_reviews = []
counter = 0
for d in df["type"]:
    counter = counter + 1
    clean_review = review_to_words( d )
    clean_train_reviews.append(clean_review)
#     d = clean_review
```


```python
len(clean_train_reviews)
```




    158



## Loading Data

## Prepare Vocabulary - BOG 

## Try to find the 15 most important words


```python
print("Creating the bag of words...\n")
from sklearn.feature_extraction.text import CountVectorizer

# Initialize the "CountVectorizer" object, which is scikit-learn's
# bag of words tool.  
vectorizer = CountVectorizer(analyzer = "word",   \
                             tokenizer = None,    \
                             preprocessor = None, \
                             stop_words = None,   \
                             min_df = 15) 

# fit_transform() Convert a collection of text documents (reviews in our example) to a matrix of token counts.
# This implementation produces a sparse representation.
# The input to fit_transform should be a list of strings.
train_data_features = vectorizer.fit_transform(clean_train_reviews)
###train_data_features = vectorizer.fit_transform(train['review'])

# Numpy arrays are easy to work with, so convert the result to an 
# array

train_data_features = train_data_features.toarray()
```

    Creating the bag of words...
    



```python
train_data_features.shape
```




    (158, 66)



## Train Model - First try simple random forest


```python
vocab = vectorizer.get_feature_names()
print(vocab[0:50])
```

    [u'add', u'also', u'american', u'apples', u'back', u'bake', u'baking', u'bananas', u'batter', u'beat', u'blueberries', u'bowl', u'brown', u'butter', u'center', u'cinnamon', u'combine', u'comes', u'cool', u'cover', u'cream', u'cup', u'cut', u'degrees', u'dish', u'egg', u'eggs', u'first', u'flour', u'grease', u'inch', u'large', u'make', u'medium', u'milk', u'minutes', u'mix', u'mixture', u'monday', u'new', u'one', u'oven', u'pan', u'place', u'pour', u'powder', u'preheat', u'preheated', u'prepared', u'remaining']



```python
import numpy as np

# Sum up the counts of each vocabulary word
dist = np.sum(train_data_features, axis=0)

# For each, print the vocabulary word and the number of times it 
# appears in the training set
for tag, count in zip(vocab, dist):
    print(count, tag)
```

    (29, u'add')
    (20, u'also')
    (22, u'american')
    (36, u'apples')
    (17, u'back')
    (50, u'bake')
    (61, u'baking')
    (22, u'bananas')
    (32, u'batter')
    (41, u'beat')
    (27, u'blueberries')
    (83, u'bowl')
    (28, u'brown')
    (58, u'butter')
    (20, u'center')
    (28, u'cinnamon')
    (37, u'combine')
    (17, u'comes')
    (38, u'cool')
    (16, u'cover')
    (32, u'cream')
    (41, u'cup')
    (19, u'cut')
    (94, u'degrees')
    (19, u'dish')
    (21, u'egg')
    (20, u'eggs')
    (33, u'first')
    (69, u'flour')
    (25, u'grease')
    (45, u'inch')
    (36, u'large')
    (25, u'make')
    (33, u'medium')
    (32, u'milk')
    (75, u'minutes')
    (51, u'mix')
    (67, u'mixture')
    (15, u'monday')
    (23, u'new')
    (35, u'one')
    (91, u'oven')
    (66, u'pan')
    (28, u'place')
    (35, u'pour')
    (18, u'powder')
    (43, u'preheat')
    (42, u'preheated')
    (21, u'prepared')
    (25, u'remaining')
    (21, u'said')
    (27, u'salt')
    (19, u'set')
    (23, u'smooth')
    (15, u'soda')
    (22, u'spread')
    (23, u'sprinkle')
    (71, u'stir')
    (92, u'sugar')
    (21, u'time')
    (52, u'together')
    (36, u'top')
    (19, u'two')
    (40, u'vanilla')
    (30, u'well')
    (35, u'white')


## Train the model and watch the cross validation score


```python
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import cross_val_score
import numpy as np
#split to train & test
msk = np.random.rand(len(clean_train_reviews)) < 0.8
train_x = train_data_features[msk]
test_x = train_data_features[~msk]
train_y = df.loc[msk,"text"]
test_y = df.loc[~msk,"text"]

forest = RandomForestClassifier(n_estimators = 100) 
forest = forest.fit( train_x, train_y )

forest.score(test_x,test_y)
cross_validation = cross_val_score(forest, train_data_features, df["text"], cv=8)  
print(cross_validation)
```

    [ 0.68181818  0.72727273  0.84210526  0.89473684  0.84210526  0.73684211
      0.78947368  0.63157895]


## We can see that the result are not so good - lets improve them!!

## First, lets try adding tf-id to our model as we learned at class


```python
from sklearn.feature_extraction.text import TfidfVectorizer
tfidfvectorizer = TfidfVectorizer(analyzer = "word",tokenizer = None, ngram_range=(1,3), max_features = 150, stop_words = None,min_df=5, use_idf=True)
tfidf_matrix = tfidfvectorizer.fit_transform(clean_train_reviews)
```


```python
from sklearn.ensemble import RandomForestClassifier

#split to train & test
# msk = np.random.rand(len(clean_train_reviews)) < 0.8
# train_x = tfidf_matrix[msk]
# test_x = tfidf_matrix[~msk]
# train_y = df.loc[msk,"text"]
# test_y = df.loc[~msk,"text"]
forest = RandomForestClassifier(n_estimators = 100, random_state=1) 
forest = forest.fit( train_x, train_y )

forest.score(test_x,test_y)
cross_validation2 = cross_val_score(forest, train_data_features, df["text"], cv=8)  
print(cross_validation2)
```

    [ 0.68181818  0.77272727  0.84210526  0.89473684  0.78947368  0.73684211
      0.84210526  0.68421053]


## The scores are still not so good
## lets minimize the min_df to 10


```python

# Initialize the "CountVectorizer" object, which is scikit-learn's
# bag of words tool.  
vectorizer = CountVectorizer(analyzer = "word",   \
                             tokenizer = None,    \
                             preprocessor = None, \
                             stop_words = None,   \
                             min_df = 10) 

# fit_transform() Convert a collection of text documents (reviews in our example) to a matrix of token counts.
# This implementation produces a sparse representation.
# The input to fit_transform should be a list of strings.
train_data_features = vectorizer.fit_transform(clean_train_reviews)
###train_data_features = vectorizer.fit_transform(train['review'])

# Numpy arrays are easy to work with, so convert the result to an 
# array

train_data_features = train_data_features.toarray()
```


```python

forest = RandomForestClassifier(n_estimators = 100, random_state=1) 
forest = forest.fit( train_x, train_y )
forest.score(test_x,test_y)
cross_validation3 = cross_val_score(forest, train_data_features, df["text"], cv=8)  
print(cross_validation3)
```

    [ 0.81818182  0.81818182  0.84210526  0.84210526  0.84210526  0.84210526
      0.94736842  0.68421053]



```python
from sklearn.model_selection import train_test_split
x = train_data_features
y = df['text']
train_x, test_x, train_y, test_y = train_test_split(train_data_features, y, test_size=0.2, random_state=150)
forest = forest.fit(train_x, train_y)
forest.score(test_x, test_y)
```




    0.90625



## 0.90625  % - nice results
## Much better results - lets see it in graph and make our final model 


```python

rcParams['figure.figsize'] = 8, 6
t = np.arange(1, 9, 1)
plt.plot(t, sorted(cross_validation), 'r', label='In at least 15 of the documents')
plt.plot(t, sorted(cross_validation2), 'b', label='Using tfidf')
plt.plot(t, sorted(cross_validation3), 'g', label='In at least 10 of the documents')
plt.ylabel('score')
plt.xlabel('cross validation')
plt.title('Comparing our 3 modles')
plt.legend(loc='upper center')
plt.show()
```


![png](output_42_0.png)


## We can see clearly that the green graph is the best one
