1..... Run command

	composer require intervention/image

2..... Add to providers Array

	Intervention\Image\ImageServiceProvider::class

3..... Add to aliases Array

	'Image' => Intervention\Image\Facades\Image::class

4..... In every model of which you want to save image
	
    public function setImageAttribute($value){
	    if(is_string($value)){
	        $this->attributes['image'] = ImageHelper::saveImageFromApi($value,'images'); 
	    }
	    else if(is_file($value)){
	        $this->attributes['image'] = ImageHelper::saveImage($value,'images'); 
	    }
    }
