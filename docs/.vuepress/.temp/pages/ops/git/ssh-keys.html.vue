<template><div><h1 id="github配置ssh-key" tabindex="-1"><a class="header-anchor" href="#github配置ssh-key" aria-hidden="true">#</a> GitHub配置SSH Key</h1>
<div class="custom-container tip"><svg viewBox="0 0 25 25" xmlns="http://www.w3.org/2000/svg" xml:space="preserve" style="fill-rule:evenodd;clip-rule:evenodd;stroke-linejoin:round;stroke-miterlimit:2"><path d="M297.6 258.73H296c-59.47.87-110.69 51.45-111.83 110.43-.626 36.485 16.525 71.085 45.94 92.68 17.86 13.18 29.88 33.56 33.77 56.42h67.62c4-22.82 16.13-43.3 34.16-56.74 28.589-21.097 45.496-54.587 45.496-90.118 0-30.03-12.078-58.833-33.496-79.882a113.133 113.133 0 0 0-80.06-32.79ZM265.19 550.7v26.6c0 4.84 1.17 6.43 1.17 6.43l63.72-.59V550.7h-64.89Z" style="fill:#48b884;fill-rule:nonzero" transform="matrix(.042 0 0 .042 0 -5.178)"/><path d="M297.64 123.3C133.26 123.3 0 256.56 0 420.94s133.26 297.63 297.64 297.63 297.63-133.25 297.63-297.63S462 123.3 297.64 123.3ZM385 487.57c-14.11 10.48-22.51 28.09-22.51 47.14v48.43c-.016 17.792-14.648 32.428-32.44 32.45h-64.86c-15.6 0-32.44-12-32.44-38.29v-42.82c0-19-8.21-36.4-21.93-46.52-37.882-27.85-59.959-72.44-59.14-119.45 1.46-77.24 66-141.09 143.81-142.22 38.87.19 76.89 14.37 105 42.11a143.764 143.764 0 0 1 43.14 103c-.159 45.761-21.911 88.86-58.63 116.17Z" style="fill:#48b884;fill-rule:nonzero" transform="matrix(.042 0 0 .042 0 -5.178)"/></svg><p class="custom-container-title">TIP</p>
<p>GitHub于2021-08-13停止使用账号密码登录，解决方式之一：通过SSH Key来实现登录。<br>
remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.<br>
注：只支持<code v-pre>ssh</code>的方式不支持<code v-pre>https</code>方式。<br>
例：<code v-pre>git@github.com:gitxingtools/xing.tools.git</code></p>
</div>
<h2 id="_1-检查本地是否有id-rsa-id-rsa-pub" tabindex="-1"><a class="header-anchor" href="#_1-检查本地是否有id-rsa-id-rsa-pub" aria-hidden="true">#</a> 1.检查本地是否有<code v-pre>id_rsa</code> <code v-pre>id_rsa.pub</code></h2>
<div class="language-bash ext-sh line-numbers-mode"><pre v-pre class="language-bash"><code><span class="token function">ls</span> ~/.ssh
</code></pre><div class="line-numbers" aria-hidden="true"><div class="line-number"></div></div></div><p><img src="https://oss.xing.tools/2022/10/25/16667132089226.jpg" alt="16667132089226"></p>
<h2 id="_2-生成ssh-key-若id-rsa已存在可跳过此步骤" tabindex="-1"><a class="header-anchor" href="#_2-生成ssh-key-若id-rsa已存在可跳过此步骤" aria-hidden="true">#</a> 2.生成SSH Key （若<code v-pre>id_rsa</code>已存在可跳过此步骤）</h2>
<div class="language-text ext-text line-numbers-mode"><pre v-pre class="language-text"><code>ssh-keygen -t rsa -C "email@xing.tools"
</code></pre><div class="line-numbers" aria-hidden="true"><div class="line-number"></div></div></div><h2 id="_3-将id-rsa-pub内容添加至github" tabindex="-1"><a class="header-anchor" href="#_3-将id-rsa-pub内容添加至github" aria-hidden="true">#</a> 3.将<code v-pre>id_rsa.pub</code>内容添加至GitHub</h2>
<div class="language-bash ext-sh line-numbers-mode"><pre v-pre class="language-bash"><code><span class="token comment"># 复制秘钥内容</span>
pbcopy <span class="token operator">&lt;</span> ~/.ssh/id_rsa.pub 
</code></pre><div class="line-numbers" aria-hidden="true"><div class="line-number"></div><div class="line-number"></div></div></div><p>将内容添加至<a href="https://github.com/settings/ssh/new" target="_blank" rel="noopener noreferrer">GitHub</a>
<img src="https://oss.xing.tools/2022/10/25/16667132425677.jpg" alt="16667132425677"></p>
<h2 id="_4-验证" tabindex="-1"><a class="header-anchor" href="#_4-验证" aria-hidden="true">#</a> 4.验证</h2>
<div class="language-text ext-text line-numbers-mode"><pre v-pre class="language-text"><code>ssh -T git@github.com
</code></pre><div class="line-numbers" aria-hidden="true"><div class="line-number"></div></div></div><p><img src="https://oss.xing.tools/2022/10/25/16667132824515.jpg" alt="16667132824515"></p>
</div></template>
