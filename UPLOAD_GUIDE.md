# 上传指南 - Upload Guide

## 📤 如何上传图片

### 方法一：通过 GitHub Web 界面
1. 在 GitHub 上打开此仓库
2. 导航到相应的 `images/` 子目录
3. 点击 "Add file" → "Upload files"
4. 拖拽或选择要上传的图片文件
5. 填写提交信息并提交

### 方法二：通过 Git 命令行
```bash
# 克隆仓库
git clone https://github.com/ASSASSINs2066/picture-host.git
cd picture-host

# 添加图片到相应目录
cp /path/to/your/image.png images/avatars/

# 提交更改
git add images/avatars/image.png
git commit -m "Add new avatar image"
git push origin main
```

### 方法三：通过 GitHub Desktop
1. 克隆仓库到本地
2. 将图片文件复制到相应目录
3. 在 GitHub Desktop 中提交更改
4. 推送到远程仓库

## 📝 文件命名规范

### 推荐格式
- `avatar_用途_日期.格式` → `avatar_github_2024_01.png`
- `screenshot_项目_日期.格式` → `screenshot_project_2024_01_15.png`
- `photo_事件_日期.格式` → `photo_vacation_2024_summer.jpg`
- `icon_名称_尺寸.格式` → `icon_app_64x64.png`

### 命名规则
✅ **推荐做法：**
- 使用英文字母和数字
- 使用下划线 `_` 或短横线 `-` 分隔
- 包含有意义的描述
- 添加日期信息
- 保持名称简洁

❌ **避免做法：**
- 使用空格
- 使用特殊字符（除了 `_` 和 `-`）
- 过长的文件名
- 纯数字命名
- 中文字符（可能导致兼容性问题）

## 📏 图片建议

### 文件大小
- 头像：建议 < 500KB
- 截图：建议 < 2MB
- 照片：建议 < 5MB
- 图标：建议 < 100KB

### 分辨率建议
- 头像：200x200 到 512x512 像素
- 截图：保持原始分辨率，但考虑压缩
- 图标：常见尺寸（16x16, 32x32, 64x64, 128x128）

### 格式选择
- **PNG**：透明背景、图标、截图
- **JPG**：照片、大尺寸图片
- **WebP**：现代浏览器，更小文件大小
- **SVG**：矢量图标、logo
- **GIF**：简单动画

## 🔒 隐私和安全

⚠️ **重要提醒：**
- 这是一个**公开仓库**，任何人都可以访问
- 不要上传包含个人敏感信息的图片
- 不要上传版权受保护的内容
- 考虑在图片中添加水印以保护版权

## 🛠️ 批量操作

### 批量上传脚本示例
```bash
#!/bin/bash
# 批量上传图片到指定目录

CATEGORY="screenshots"  # 修改为目标目录
DATE=$(date +"%Y_%m_%d")

for file in *.png *.jpg *.jpeg; do
    if [[ -f "$file" ]]; then
        # 重命名文件包含日期
        new_name="${CATEGORY}_${DATE}_${file}"
        cp "$file" "images/${CATEGORY}/${new_name}"
        echo "Added: $new_name"
    fi
done

git add images/${CATEGORY}/
git commit -m "Batch upload ${CATEGORY} images - ${DATE}"
git push origin main
```

## 📊 管理建议

1. **定期清理**：删除不再需要的旧图片
2. **备份重要图片**：考虑在其他地方也保存重要图片
3. **使用分支**：对于大量更改，可以使用分支进行管理
4. **文档更新**：及时更新相关文档和链接

## 🔗 相关链接

- [主README](./README.md)
- [GitHub Pages 预览](https://assassins2066.github.io/picture-host/)
- [仓库设置](../../settings)