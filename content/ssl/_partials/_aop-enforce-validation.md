---
_build:
  publishResources: false
  render: never
  list: never
---

Once you can confirm everything is working as expected for your specific origin setup, configure your origin to enforce the authentication.

<details>
<summary>Apache example</summary>
<div>

```txt
SSLVerifyClient require
```

</div>
</details>

<details>
<summary>NGINX example</summary>
<div>

```txt
ssl_verify_client on;
```

</div>
</details>

After completing the process, you can use `curl` to send requests directly to your origin IPs, verifying that the requests fail due to certificate validation being enforced.