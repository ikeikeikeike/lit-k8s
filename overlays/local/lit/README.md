## TODO

Resource Limits

## Usage

Create `lit` namespace

```php
$ kubectl create namespace lit
```

Create all of resources to production

```php
$ kustomize build . | kubectl apply -f -
```

Migrate by [lit-migration](https://example.com)

```php
$ kustomize build migrate | kubectl apply -f -
```

Make sure resource available.

```php
$ kubectl get po,deploy,sts,svc,job,ing,pv,pvc,endpoints -n lit
```

Show this environment(production) logs. (You might need to install [stern](https://github.com/wercker/stern))

```php
$ stern production -n lit
```

Setup nginx

* Disable other things listening on port 80 / 443 on your Mac:
  * (You might need to `sudo brew services stop launch_socket_server`)

Visit http://127.0.0.1.xip.io/, which should show an lit top page.

```
$ open http://127.0.0.1.xip.io
```

**Delete all of resources to production**

```php
$ kustomize build . | kubectl delete -f -
```

