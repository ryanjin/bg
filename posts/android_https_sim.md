---
title: android_https_sim
date: '2013-09-04'
description:
categories:
---

android中webview访问https连接的证书问题
===

有SIM卡的时候，通过手机浏览器访问https不会跳出证书不安全的确认框;但是没有SIM卡的时候，访问https会跳出来证书确认框。

webview中需要实现

	@Override
    public void onReceivedSslError(WebView view, SslErrorHandler handler, SslError error) {
	    handler.proceed();
    }

来进行确认证书，这样就执行下去了。默认是

    public void onReceivedSslError(WebView view, SslErrorHandler handler,
            SslError error) {
        handler.cancel();
    }

所以就跳过了