 
 Сборка проекта на реакт для хостинга
 Сначала попробовать просто прописать homePage 
 npm run build
 npm install -g serve
  serve -s build
  
  <IfModule mod_rewrite.c>

  RewriteEngine On
  RewriteBase /
  RewriteRule ^index\.html$ - [L]
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteCond %{REQUEST_FILENAME} !-l
  RewriteRule . /index.html [L]


</IfModule>
 
 
 
 @media screen and (min-width: 320px) and (max-width: 767px) {

}

/* //----------------------------------------------------------------------TABLET----------------------------------------------------- */
@media screen and (min-width: 768px) and (max-width: 1199px) {
    
}
/* "//-------------------------------------------------------DESKTOP----------------------------------------------------------------- */
@media (min-width: 1200px) {

}

 
 
 
 ФОРМУЛА РАССЧЕТА РАЗМЕРА ЕЛЕМЕНТА В ТАБЛИЦЕ.
 --item: 2; // количество елементов в стороке.
  --indent: 30px; гэп.
  flex-basis: calc((100% - var(--indent) * (var(--item) - 1)) / var(--item));


@mixin mq($screen) {
	$mobile: 480px;
	$tablet: 768px;
	$desktop: 1366px;
-------------------------миксин для все экранов------------------
	@if $screen == mobile-only {
		@media screen and (max-width: #{$tablet - 0.02}) {
			@content;
		}
	} @else if $screen == mobile-only-land {
		@media screen and (max-width: #{$tablet - 0.02}) and (orientation: landscape) {
			@content;
		}
	} @else if $screen == mobile-small {
		@media screen and (max-width: #{$mobile - 0.02}) {
			@content;
		}
	} @else if $screen == mobile {
		@media screen and (min-width: $mobile) {
			@content;
		}
	} @else if $screen == tablet-only {
		@media screen and (min-width: $tablet) and (max-width: #{$desktop - 0.02}) {
			@content;
		}
	} @else if $screen == tablet {
		@media screen and (min-width: $tablet) {
			@content;
		}
	} @else if $screen == desktop {
		@media screen and (min-width: $desktop) {
			@content;
		}
	} @else if $screen == notDesktop {
		@media screen and (max-width: #{$desktop - 0.02}) {
			@content;
		}
	} @else if $screen == retina {
		@media screen and (min-device-pixel-ratio: 2),
			screen and (-moz-min-device-pixel-ratio: 2),
			screen and (-o-min-device-pixel-ratio: 2/1),
			screen and (-webkit-min-device-pixel-ratio: 2),
			screen and (min-resolution: 192dpi),
			screen and (min-resolution: 2dppx) {
			@content;
		}
	}
}
