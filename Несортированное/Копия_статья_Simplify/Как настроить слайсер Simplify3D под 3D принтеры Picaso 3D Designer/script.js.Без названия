window.recaptcha.token = '';

window.recaptcha.stid = null; // setTimeout id

window.recaptcha.reloadToken = function()
{
    if (typeof(grecaptcha) === 'undefined') return;

    clearTimeout(this.stid);

    this.stid = setTimeout(() =>
    {
        this.reloadToken();
    },
    this.tokenLifeTime * 1000);

    grecaptcha.ready(() =>
    {
        grecaptcha.execute(this.siteKey, {action: 'homepage'}).then(token =>
        {
            this.token = token;
        });
    });
};

window.recaptcha.getToken = function() // пользуемся этим методом когда нужно получить токен
{
    var oldToken = this.token;
    this.reloadToken();
    return oldToken;
};

document.addEventListener('DOMContentLoaded', function()
{
    window.recaptcha.reloadToken();

    document.querySelectorAll('input[name=recaptcha_token]').forEach(item =>
    {
        item.form.onsubmit = () =>
        {
            item.value = window.recaptcha.getToken();
        };
    });
});