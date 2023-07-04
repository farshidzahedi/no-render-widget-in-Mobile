# no-render-widget-in-Mobile
جلوگیری از رندر المان ها در حالت موبایل 
در فایل Fuction.php این کد را اضافه کنید
//php tag

function hide_content_on_mobile($content) {
    if (is_mobile() && preg_match('/<div class=".*?\belementor-hidden-mobile\b.*?">(.*?)<\/div>/s', $content, $matches)) {
        $content = str_replace($matches[0], '', $content);
    }
    return $content;
}
add_filter('the_content', 'hide_content_on_mobile');



//php end

![download](https://github.com/farshidzahedi/no-render-widget-in-Mobile/assets/68387753/5d938da9-de58-4da1-a4a7-0a55af361a28)

اگر از وردپرس و صفحه ساز المنتور استفاده می کید بعضی اوقات مجبور هستید یک ویجت را در حالت موبایل مخفی کنید !!
اما مشکل از انجایی شروع می شود که این ویجت در DOM رندر می شود و فقط حالت نمایش آن None شده. با استفاده از این کد شما میتوانید با فعال کردن حالت مخفی در المنتور بصورت خودکار مانع رندر ویجت های اضافه شوید و Performance بالاتری دریافت خواهید کرد

موفق باشید
