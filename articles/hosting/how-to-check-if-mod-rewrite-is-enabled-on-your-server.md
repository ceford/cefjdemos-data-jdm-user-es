<!-- Filename: How_to_check_if_mod_rewrite_is_enabled_on_your_server / Display title: Cómo verificar si mod_rewrite está activo en tu servidor -->

Muchos problemas de SEO aparecen cuando un servidor no tiene activo
mod_rewrite (en Apache). Puedes verificar si esta configuración es
correcta o no y si por este motivo estás teniendo errores HTTP 500.

A continuación el procedimiento para comprobar si mod_rewrite está
activo:

**1. Activa SEO en el administrador:**

Site -\> Global Configuration -\> SEO Settings: Search Engine Friendly
URLs to Yes, Use URL Rewriting to Yes. (Setting Add suffix to URLs is
optional).

  
**2. Rename your htaccess.txt to .htaccess:**

Next place ONLY the following lines in your .htaccess:

    RewriteEngine On
    Options +FollowSymLinks
    RewriteRule ^joomla\.html http://www.joomla.org/? [R=303,L]

  
**3. Now point your browser to:**
<a href="http://www.example.com/joomla.html" class="external free"
target="_blank"
rel="nofollow noreferrer noopener">http://www.example.com/joomla.html</a>

(Replace www.example.com with your own domain name in the URL above.)

If it redirects you to joomla.org then mod_rewrite is working. If it
gives you an error then mod_rewrite is not working.

Note: if your site is located in a folder such as "/test/" you need to
insert the code in the root .htaccess file as follows:

    RewriteEngine On
    Options +FollowSymLinks
    RewriteRule ^test/joomla\.html http://www.joomla.org/? [R=303,L]
