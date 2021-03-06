<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

# Laravel Sgopping

Laravel shopping is built in laravel 8 version and MySQL database for the backend. It has different features for the user like a user can view all the category, select a product and select the quantity and add the product to his cart. The user can add multiple products in cart . There are mutliple payment methods in the checkout page.

## Git clone
git clone https://github.com/Enas-Asmar/laravel-shopping.git


## Change directory
cd laravel-shopping




## Install Dependencies
composer install




## Run Server
php artisan serve




## Click below after setup
http://localhost:8000





# Usage
The shoppingcart gives you the following methods to use:

## addToCart(Request ...)
    
$cart= new Cart;
    
$cart->user_id=$req->session()->get('user')['id'];
    
$cart->product_id=$req->product_id;
    
$cart->save();



## CartItem()

$userId=Session()->get('user')['id'];

return Cart::where('user_id',$userId)->count();


## CartList()

$userId=Session()->get('user')['id'];

$products= DB::table('cart')

->join('products','cart.product_id','=','products.id')

->where('cart.user_id',$userId)

->select('products.*','cart.id as cart_id')

->get();

return view('cartlist',['products'=>$products]);



## RemoveCart($id)
    
Cart::destroy($id);

return redirect('cartlist');





# Overiew

-Login and Register

-Product quantity increment/decrement before adding to cart

-Add to Cart.

-Add to cart with product quantity increment/decrement from the Cart .

-Checkout information validation before placing order

-Checkout Page.

-Multiple payment option.

-View orders and order status.





