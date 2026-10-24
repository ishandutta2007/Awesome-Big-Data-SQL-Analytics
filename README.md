# Awesome-Big-Data-SQL-Analytics

$repoName = (Get-Item .).Name
$block = @"

## ⭐ Star History

[![Star History Chart](https://star-history.dera.page/svg?repos=ishandutta2007/$repoName&type=date&legend=top-left)](https://star-history.dera.page/#ishandutta2007/$repoName&type=date&legend=top-left)
"@

$content = Get-Content README.md -Raw
if ($content -notmatch [regex]::Escape('Star History Chart')) {
    Add-Content -Path README.md -Value $block -Encoding utf8
    Write-Host "Star History section appended." -ForegroundColor Green
} else {
    Write-Host "Star History section already present — skipping." -ForegroundColor Yellow
}

git add README.md
git commit -m "docs: add Star History section"
git push
