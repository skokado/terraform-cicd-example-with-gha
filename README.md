# Terraform CI/CD GitHub Actions サンプル

GitHub ActionsとTerraformのCI/CDリファレンス実装

## 構成
- 環境分離
    - `envs/dev/`
    - `envs/stg/`
- 環境ごとの CI/CD ワークフロー
    - `terraform-dev.yaml`
    - `terraform-stg.yaml`
- **再利用可能ワークフロー（重要）**: `.github/workflows/reusable-job-terraform.yaml`

ref. https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows

## Tips

### .terraform.lock.hcl のマルチプラットフォーム対応

amd64 (x86_64), arm64 や MacOS に対応した `.terraform.lock.hcl` を生成するには、以下のコマンドを使用します。

```
terraform providers lock \
  -platform=linux_amd64 \
  -platform=linux_arm64 \
  -platform=darwin_amd64 \
  -platform=darwin_arm64
```
