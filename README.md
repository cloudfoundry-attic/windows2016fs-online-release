# windows2016fs-online-release

A [BOSH](http://docs.cloudfoundry.org/bosh/) release for deploying [windows2016fs](https://github.com/cloudfoundry-incubator/windows2016fs/tree/master/1709).

**Note:**

This release assumes your BOSH installation has internet access at deploy time.

## smoke test

Ensure that `winc-release` and `windows2016fs-release` are uploaded to your BOSH director.

```
bosh -d windows2016fs deploy manifests/smoke-test.yml \
  -v fs-version="windows2016fs" \
  -v stemcell-os="windows2016" \
  -v smoke-test-name="windows2016fs-smoke-test" \
  -v cached-image-uris=["oci:///C:/var/vcap/packages/windows2016fs"]
bosh -d windows2016fs run-errand smoke-test
```
