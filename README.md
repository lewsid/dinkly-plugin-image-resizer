Dinkly Image Resizer Plugin v1.00
=================================

Resize images in your Dinkly project on the fly


Installation
------------

  1. Move the `image_resizer` folder into your dinkly project's `plugins` folder.

  2. Add the following lines under the `plugins` section of your `config/config.yml` file:

  ```yaml
  image_resizer:
    apps:
        image:
            base_href: /image        
            app_name: Handler
            enabled: true
            default_module: handler
            files_directory: uploads
  ```

  3. Create an `uploads` folder under your `web` directory and set the file permissions to ensure that it's writeable:

     `mkdir web/uploads`

     `chown -R www-data:www-data web/uploads`

     `chmod -R 777 web/uploads`


Usage
-----

Image resizer is designed to allow you to specify in the template the dimensions you want an image to be served. The resizer automatically creates a resized version of the image on the fly and then utilizes that resized version going forward. In a template you would put something like:

```
<img src="/image/handler/image/cropped/false/w/500/h/315/file_name/my_image.png">
```

This would create a file named `cropped-500-315-my_image.png` inside of a `web/uploads/resized/` folder.  This can be a great time saver for frontend responsive development allowing you to drop the orginal file into the uploads folder and simply specifying the various sizes needed in each template.


License
-------

The Dinkly Image Resizer plugin is open-sourced software licensed under the MIT License.


Contact
-------

  - lewsid@lewsid.com (github.com/lewsid), andrew@bluehousegroup.com (github.com/andrewvt)
