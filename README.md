Cloud-Ready Blog Platform
License: AGPL v3
Docker Image CI

一个支持多用户、Markdown写作、全文搜索的博客平台，适配云原生部署。

核心特性
多用户认证（JWT + OAuth2）

Markdown编辑器（支持版本历史）

全文搜索（Elasticsearch）

文件存储（兼容S3）

响应式设计

自动化Docker部署

markdown
## 技术架构
### 前端
- Next.js 14 (App Router)
- Shadcn UI + Tailwind CSS
- React Query
- Tiptap Markdown编辑器

### 后端
- Go 1.21 (Gin框架)
- PostgreSQL 15
- Redis 7 (缓存和会话)
- Elasticsearch 8
- MinIO (S3兼容存储)

### 基础设施
- Docker + Docker Compose
- GitHub Actions
- Nginx
- Prometheus + Grafana (监控)

## 项目结构
cloud-blog-platform/
├── apps
│ ├── frontend/ # 前端应用
│ └── backend/ # Go后端服务
├── infra/ # 基础设施配置
│ ├── nginx/
│ ├── prometheus/
│ └── docker-compose.prod.yml
├── scripts/ # 部署脚本
├── .github/ # CI/CD工作流
├── docker-compose.yml # 开发环境配置
└── README.md

VPS部署指南
前置准备
Ubuntu 22.04 LTS 服务器

已安装 Docker 和 Docker Compose

域名指向服务器IP

安全实践
使用fail2ban防止暴力破解

配置自动化的Docker安全扫描

启用自动的Let's Encrypt证书续期

定期进行数据库备份到S3存储

使用crowdsec进行实时威胁检测

扩展建议
添加CDN支持

实现文章导出为PDF

集成第三方登录（GitHub/Google）

添加评论系统

实现基于角色的访问控制（RBAC）

许可证
AGPL-3.0 License - 详见 LICENSE


### 架构优势
1. **云原生设计**：所有组件容器化，方便迁移和扩展
2. **混合部署能力**：支持本地开发、GitHub托管和VPS部署
3. **成本优化**：使用MinIO替代商业S3存储，PostgreSQL替代云数据库
4. **可观测性**：集成Prometheus监控和日志聚合
5. **安全加固**：包含生产环境最佳安全实践

这个项目模板提供了从代码开发到生产部署的完整链路，特别适合需要自主掌控数据同时保持GitHub协作优势的场景。所有服务都经过容器化封装，可以在任何支持Docker的环境快速部署。# Cloud-Ready-Blog-Platform
