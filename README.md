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
