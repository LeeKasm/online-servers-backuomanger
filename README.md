# online-servers-backuomanger
针对online的VPS 用于在线备份当前系统
<div class="page ">

              <div class="pull-right hidden-print">
  <div class="toc-affix affix" data-spy="affix" data-offset-top="150">
    <!-- TOC START -->
<div class="panel panel-default" id="dw__toc" style="background-color: rgb(255, 255, 255);">
<h3 class="panel-heading toggle closed" style="cursor: pointer;" id="table-of-contents"><i class="fa fa-fw fa-list" style="padding-right: 5px"></i> <strong class="fa fa-fw fa-chevron-down"><span><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">+</font></font></span></strong><span class="label hide"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">目录</font></font></span><a class="anchorjs-link " href="#table-of-contents" aria-label="Anchor link for: table of contents" data-anchorjs-icon="" style="font-family: anchorjs-icons; font-style: normal; font-variant: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h3>
<div class="panel-body" style="display: none;" aria-expanded="false">

<ul class="nav  nav-pills nav-stacked toc" style="display: none;">
<li class="level2"><a href="#backup_manager_gnulinux"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">备份管理器（GNU / Linux）</font></font></a>
<ul class="nav  nav-pills nav-stacked toc">
<li class="level3"><a href="#step_0requirements"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第0步：要求</font></font></a></li>
<li class="level3"><a href="#step_1installation_of_backup_manager"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第1步：安装备份管理器</font></font></a></li>
<li class="level3"><a href="#step_2configuration_of_backup_manager"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第2步：配置备份管理器</font></font></a></li>
<li class="level3"><a href="#step_3automatization_of_backups"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第3步：备份自动化</font></font></a></li>
<li class="level3"><a href="#step_4recovery_of_backups"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第4步：恢复备份</font></font></a></li>
</ul>
</li>
<li class="level2"><a href="#references"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">参考</font></font></a></li>
</ul>
</div>
</div>
<!-- TOC END -->
  </div>
</div>

<h2 class="sectionedit1" id="backup_manager_gnulinux"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">备份管理器（GNU / Linux）</font></font><a class="anchorjs-link " href="#backup_manager_gnulinux" aria-label="Anchor link for: backup_manager_gnulinux" data-anchorjs-icon="" style="font-family: anchorjs-icons; font-style: normal; font-variant: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h2>
<div class="level2">
<div class="notetip"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要求：</font></font></strong><ul class="fix-media-list-overlap">
<li class="level1"><div class="li"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您在</font><a href="https://console.online.net" class="urlextern" title="https://console.online.net" rel="nofollow"><font style="vertical-align: inherit;">console.online.net上</font></a><font style="vertical-align: inherit;">有一个帐户</font></font><a href="https://console.online.net" class="urlextern" title="https://console.online.net" rel="nofollow"><font style="vertical-align: inherit;"></font></a><br>
</div>
</li>
<li class="level1"><div class="li"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">你有一个</font></font><a href="https://www.online.net/en/dedicated-server" class="urlextern" title="https://www.online.net/en/dedicated-server" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Dedibox</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">专用服务器</font></font></div>
</li>
<li class="level1"><div class="li"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您已</font><font style="vertical-align: inherit;">在管理控制台中</font><font style="vertical-align: inherit;">配置了</font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Dedibackup</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">帐户</font></font></div>
</li>
</ul>

</div>
<p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
备份管理器是一种软件，可用于在</font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Dedibackup </font></font></strong> <abbr title="文件传输协议"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">FTP</font></font></abbr><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">空间</font><font style="vertical-align: inherit;">上自动备份服务器</font><font style="vertical-align: inherit;">。 
</font></font></p>

</div>

<h3 class="sectionedit2" id="step_0requirements"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第0步：要求</font></font><a class="anchorjs-link " href="#step_0requirements" aria-label="Anchor link for: step_0requirements" data-anchorjs-icon="" style="font-family: anchorjs-icons; font-style: normal; font-variant: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h3>
<div class="level3">
<ul class="fix-media-list-overlap">
<li class="level1"><div class="li"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 有一个GNU / Linux发行版</font></font></div>
</li>
<li class="level1"><div class="li"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">曾经</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">的gettext</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Perl的</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">安装</font></font></div>
</li>
</ul>

</div>

<h3 class="sectionedit3" id="step_1installation_of_backup_manager"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第1步：安装备份管理器</font></font><a class="anchorjs-link " href="#step_1installation_of_backup_manager" aria-label="Anchor link for: step_1installation_of_backup_manager" data-anchorjs-icon="" style="font-family: anchorjs-icons; font-style: normal; font-variant: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h3>
<div class="level3">
<pre class="code"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">apt-get install backup-manager</font></font></pre>

</div>

<h3 class="sectionedit4" id="step_2configuration_of_backup_manager"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第2步：配置备份管理器</font></font><a class="anchorjs-link " href="#step_2configuration_of_backup_manager" aria-label="Anchor link for: step_2configuration_of_backup_manager" data-anchorjs-icon="" style="font-family: anchorjs-icons; font-style: normal; font-variant: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h3>
<div class="level3">

<p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以</font><strong><font style="vertical-align: inherit;">root </font></strong></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">身份</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">登录时</font><font style="vertical-align: inherit;">
编辑文件</font><strong><font style="vertical-align: inherit;">/etc/backup-manager.conf</font></strong></font><strong><font style="vertical-align: inherit;"></font></strong>
</p>
<pre class="code"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">root @dedibox：/ home / bertrand #nano /etc/backup-manager.conf</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
...</font></font></pre>

<p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
遵循最常见的选项：
</font></font></p>
<div class="table sectionedit5 table-responsive"><table class="inline table table-striped table-condensed">
	<tbody><tr class="row0">
		<td class="col0 leftalign"> <em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">选项的名称</font></font></strong></em>       </td><td class="col1 leftalign"> <em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">值的示例</font></font></strong></em>           </td><td class="col2 leftalign"> <em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">描述</font></font></strong></em>                                                                                                                          </td>
	</tr>
	<tr class="row1">
		<th class="col0 leftalign" colspan="3"> <strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">本地存储</font></font></strong>                                                                                                                                                                                               </th>
	</tr>
	<tr class="row2">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_REPOSITORY_ROOT            </font></font></td><td class="col1 leftalign"> <code>“/var/archives”</code>                 </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 用于存储存档的本地文件夹                                                                                                     </font></font></td>
	</tr>
	<tr class="row3">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_ARCHIVE_TTL                </font></font></td><td class="col1 leftalign"> <code>“3”</code>                             </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 要在本地存储的档案数量                                                                                          </font></font></td>
	</tr>
	<tr class="row4">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_ARCHIVE_METHOD             </font></font></td><td class="col1"> <code>“tarball-incremental mysql svn”</code> </td><td class="col2"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要使用的存档方法。</font><font style="vertical-align: inherit;">可以是</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">一个</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">几个</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，这些值：</font></font><code>tarball</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，</font></font><code>tarball-incremental</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，</font></font><code>mysql</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>svn</code> </td>
	</tr>
	<tr class="row5">
		<th class="col0 leftalign" colspan="3"> <strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要归档的元素</font></font></strong>                                                                                                                                                                                          </th>
	</tr>
	<tr class="row6">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_TARBALL_DIRECTORIES        </font></font></td><td class="col1 leftalign"> <code>“/etc /home”</code>                    </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 要备份的文件夹列表                                                                                                          </font></font></td>
	</tr>
	<tr class="row7">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_TARBALL_BLACKLIST          </font></font></td><td class="col1"> <code>“/var/archives /home/notbackup”</code> </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 最终要排除的子文件夹                                                                                                    </font></font></td>
	</tr>
	<tr class="row8">
		<th class="col0 leftalign" colspan="3"> <strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">转移到远程存储</font></font></strong>                                                                                                                                                                          </th>
	</tr>
	<tr class="row9">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_UPLOAD_METHOD              </font></font></td><td class="col1 leftalign"> <code><strong>“ftp”</strong></code>                       </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 传输备份的方法                                                                                              </font></font></td>
	</tr>
	<tr class="row10">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">BM_UPLOAD_ </font></font><abbr title="文件传输协议"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">FTP</font></font></abbr><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> _USER            </font></font></td><td class="col1 leftalign"> <code><strong>“sd-000”</strong></code>                    </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">识别用于</font></font><abbr title="文件传输协议"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">FTP</font></font></abbr><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">服务器                                                                                      </font></font></td>
	</tr>
	<tr class="row11">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">BM_UPLOAD_ </font></font><abbr title="文件传输协议"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">FTP</font></font></abbr><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> _PASSWORD        </font></font></td><td class="col1 leftalign"> <code><strong>“mYp4SsW0rd”</strong></code>                </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 以前指定的用户的密码                                                                                               </font></font></td>
	</tr>
	<tr class="row12">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">BM_UPLOAD_ </font></font><abbr title="文件传输协议"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">FTP</font></font></abbr><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> _HOSTS           </font></font></td><td class="col1 leftalign"> <code><strong>“dedibackup.dedibox.fr”</strong></code>     </td><td class="col2 leftalign"><font style="vertical-align: inherit;"></font><abbr title="文件传输协议"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">FTP</font></font></abbr><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">服务器的                                                                                                                            </font><font style="vertical-align: inherit;">名称</font></font></td>
	</tr>
	<tr class="row13">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">BM_UPLOAD_ </font></font><abbr title="文件传输协议"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">FTP</font></font></abbr><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> _PASSIVE           </font></font></td><td class="col1 leftalign"> <code>“true”</code>     </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 激活被动传输模式                                                                                                                           </font></font></td>
	</tr>
	<tr class="row14">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">BM_UPLOAD_ </font></font><abbr title="文件传输协议"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">FTP</font></font></abbr><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> _PURGE           </font></font></td><td class="col1 leftalign"> <code>“true”</code>                          </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在转移（</font></font><code>true</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或</font></font><code>false</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）                                                                  </font><font style="vertical-align: inherit;">之前删除目录内容</font></font></td>
	</tr>
	<tr class="row15">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">BM_UPLOAD_ </font></font><abbr title="文件传输协议"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">FTP</font></font></abbr><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> _DESTINATION     </font></font></td><td class="col1 leftalign"> <code>“/”</code>                             </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 要复制的文件的目标文件夹（注意：它已存在于服务器上）                                   </font></font></td>
	</tr>
	<tr class="row16">
		<th class="col0 leftalign" colspan="3"> <strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">增量存档</font></font></strong>                                                                                                                                                                                        </th>
	</tr>
	<tr class="row17">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_TARBALLINC_MASTERDATETYPE  </font></font></td><td class="col1 leftalign"> <code>“monthly”</code>                       </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">创建</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">完整</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">档案的</font><font style="vertical-align: inherit;">频率</font><font style="vertical-align: inherit;">。</font><font style="vertical-align: inherit;">可以是每日（</font></font><code>daily</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）或每月（</font></font><code>monthly</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）                               </font></font></td>
	</tr>
	<tr class="row18">
		<td class="col0"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_TARBALLINC_MASTERDATEVALUE </font></font></td><td class="col1 leftalign"> <code>“23”</code>                            </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">创建</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">完整</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">存档的日期（从1（星期一）到7（星期日）进行每日备份，从1到31进行每月备份）         </font></font></td>
	</tr>
	<tr class="row19">
		<th class="col0 leftalign" colspan="3"> <strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">MySQL数据库</font></font></strong>                                                                                                                                                                                         </th>
	</tr>
	<tr class="row20">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_MYSQL_DATABASES            </font></font></td><td class="col1 leftalign"> <code>“mysql”</code>                         </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> MySQL数据库的名称                                                                                                               </font></font></td>
	</tr>
	<tr class="row21">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_MYSQL_ADMINLOGIN           </font></font></td><td class="col1 leftalign"> <code>“root”</code>                          </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 用于连接MySQL服务器的标识符                                                                                    </font></font></td>
	</tr>
	<tr class="row22">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_MYSQL_ADMINPASS            </font></font></td><td class="col1 leftalign"> <code>“”</code>                              </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 与先前指定的标识符关联的密码                                                                                        </font></font></td>
	</tr>
	<tr class="row23">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_MYSQL_HOST                 </font></font></td><td class="col1 leftalign"> <code>“localhost”</code>                     </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> MySQL服务器的名称                                                                                                                          </font></font></td>
	</tr>
	<tr class="row24">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_MYSQL_PORT                 </font></font></td><td class="col1 leftalign"> <code>“3306”</code>                          </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> MySQL服务器的侦听端口                                                                                                               </font></font></td>
	</tr>
	<tr class="row25">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_MYSQL_FILETYPE             </font></font></td><td class="col1 leftalign"> <code>“gzip”</code>                          </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">备份存档（</font></font><code>gzip</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或</font></font><code>bzip2</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）的                                                               </font><font style="vertical-align: inherit;">压缩格式</font></font></td>
	</tr>
	<tr class="row26">
		<th class="col0 leftalign" colspan="3"> <strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SVN服务器</font></font></strong>                                                                                                                                                                                                  </th>
	</tr>
	<tr class="row27">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_SVN_REPOSITORIES           </font></font></td><td class="col1 leftalign"> <code>“”</code>                              </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> SVN的绝对路径                                                                                                        </font></font></td>
	</tr>
	<tr class="row28">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_SVN_COMPRESSWITH           </font></font></td><td class="col1 leftalign"> <code>“gzip”</code>                          </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SVN备份（</font></font><code>gzip</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或</font></font><code>bzip2</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）的                                                                      </font><font style="vertical-align: inherit;">压缩格式</font></font></td>
	</tr>
	<tr class="row29">
		<th class="col0 leftalign" colspan="3"> <strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">高级</font></font></strong>                                                                                                                                                                                                       </th>
	</tr>
	<tr class="row30">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_PRE_BACKUP_COMMAND          </font></font></td><td class="col1 leftalign"> <code>“”</code>                              </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 允许在启动Manager之前执行脚本                                                                      </font></font></td>
	</tr>
	<tr class="row31">
		<td class="col0 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> BM_POST_BACKUP_COMMAND         </font></font></td><td class="col1 leftalign"> <code>“”</code>                              </td><td class="col2 leftalign"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 允许在备份管理器的最后一个操作之后执行脚本                                                                      </font></font></td>
	</tr>
</tbody></table></div>

<p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
有关其他配置选项的更多信息，请参阅</font></font><a href="http://www.backup-manager.org/documentation/" class="urlextern" title="http://www.backup-manager.org/documentation/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">官方文档</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。
</font></font></p>

</div>

<h3 class="sectionedit6" id="step_3automatization_of_backups"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第3步：备份自动化</font></font><a class="anchorjs-link " href="#step_3automatization_of_backups" aria-label="Anchor link for: step_3automatization_of_backups" data-anchorjs-icon="" style="font-family: anchorjs-icons; font-style: normal; font-variant: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h3>
<div class="level3">

<p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
为了自动化我们服务器的备份，我们使用一个小脚本和</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">cron</font></font></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。
</font></font></p>
<ul class="fix-media-list-overlap">
<li class="level1"><div class="li"> <strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">创建脚本</font></font></strong></div>
</li>
</ul>

<p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
将以下内容复制/粘贴到shell中：
</font></font></p>
<pre class="code"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">cat &lt;&lt; EOF&gt; /etc/backup-manager.sh&amp;&amp; chmod 700 /etc/backup-manager.sh</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
＃！/ bin / sh的</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
test -x / usr / sbin / backup-manager || </font><font style="vertical-align: inherit;">退出0</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
/ usr / sbin目录/备份管理器</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
EOF</font></font></pre>
<ul class="fix-media-list-overlap">
<li class="level1"><div class="li"> <strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用crontab将其添加到cron</font></font></strong></div>
</li>
</ul>
<pre class="code"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">root @ dedibox：〜＃crontab -e</font></font></pre>

<p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
添加以下行以运行备份管理器...
</font></font></p>

<p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
...每隔15天8:04
</font></font></p>
<pre class="code"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">4 8 * / 15 * * /etc/backup-manager.sh</font></font></pre>

<p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
... 2月4日23:16
</font></font></p>
<pre class="code"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">16 23 4 2 * /etc/backup-manager.sh</font></font></pre>

<p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
...周一至周五8:04
</font></font></p>
<pre class="code"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">4 8 * * 1-5 /etc/backup-manager.sh</font></font></pre>

</div>

<h3 class="sectionedit7" id="step_4recovery_of_backups"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第4步：恢复备份</font></font><a class="anchorjs-link " href="#step_4recovery_of_backups" aria-label="Anchor link for: step_4recovery_of_backups" data-anchorjs-icon="" style="font-family: anchorjs-icons; font-style: normal; font-variant: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h3>
<div class="level3">
<ul class="fix-media-list-overlap">
<li class="level1"><div class="li"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您只需要连接到服务器</font></font><code>dedibackup.dedibox.fr</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></div>
</li>
</ul>
<pre class="code"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">bertrand @ dedibox：〜$ ftp -n dedibackup.dedibox.fr</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
连接到dedibackup.dedibox.fr。</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
220-FTP服务器就绪。</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
220 Ceci est un systeme prive  -  Aucun utilisateur anonyme autorise</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
远程系统类型是UNIX。</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
使用二进制模式传输文件。</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
ftp&gt;用户sd-000 mYp4SsW0rd</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
331 Utilisateur sd-000好的。</font><font style="vertical-align: inherit;">Veuillez taper votre mot de passe</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
230-L'utilisateur sd-000 a un acces de groupe sur：1000 106 105</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
230-104 46 44 30 29 25 24 20</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
230-4</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
230-OK。</font><font style="vertical-align: inherit;">Le repertoire restreint courant est /</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
230 3597 Ko使用（0％） -  autorises：10240000 Ko</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
远程系统类型是UNIX。</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
使用二进制模式传输文件。</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
ftp&gt; ls</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
200名Commande PORT执行人员</font></font><font></font>
150 Connexion au port 32845<font></font>
drwxr-xr-x    2 1000     1000          216 May 31 19:36 .<font></font>
drwxr-xr-x    2 1000     1000          216 May 31 19:36 ..<font></font>
-rw-------    1 1000     1000           10 May 31 19:36 .ftpquota<font></font>
-rw-r--r--    1 1000     1000          123 May 31 19:36 dedibox-20060531.md5<font></font>
-rw-r--r--    1 1000     1000       289778 May 31 19:36 dedibox-etc.20060531.tar.gz<font></font>
-rw-r--r--    1 1000     1000      3393717 May 31 19:36 dedibox-home.20060531.tar.gz<font></font>
226-Options: -a -l<font></font>
226 6 elements au total<font></font>
ftp&gt; get dedibox-etc.20060531.tar.gz<font></font>
local: dedibox-etc.20060531.tar.gz remote: dedibox-etc.20060531.tar.gz<font></font>
200 Commande PORT executee<font></font>
150-Connexion au port 32846<font></font>
150 283.0 Koctets a downloader<font></font>
226-Fichier transfere sans probleme<font></font>
226 0.021 secondes (mesuree ici), 12.87 Moctets par seconde<font></font>
289778 bytes received in 0.03 secs (9793.3 kB/s)<font></font>
ftp&gt; bye<font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
221-Au revoir。</font><font style="vertical-align: inherit;">Vous avez uploade 0 et downloade 283 Koctets。</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
221德洛格。</font></font></pre>
<ul class="fix-media-list-overlap">
<li class="level1"><div class="li"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 检查文件是否已下载： </font></font></div>
</li>
</ul>
<pre class="code"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">bertrand @ dedibox：〜$ ls</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
dedibox-etc.20060531.tar.gz</font></font></pre>
<ul class="fix-media-list-overlap">
<li class="level1"><div class="li"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> 解压缩了</font></font></div>
</li>
</ul>
<pre class="code"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">bertrand @ dedibox：〜$ tar -xvzf dedibox-etc.20060531.tar.gz</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
等等/</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
等/ APM /</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
等/ APM / resume.d /</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
...</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
etc / profile文件</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
等/的mime.types</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
等/ bash_completion</font></font></pre>
<ul class="fix-media-list-overlap">
<li class="level1"><div class="li"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">从现在开始，我们可以恢复我们想要的文件。</font><font style="vertical-align: inherit;">例如…</font></font></div>
</li>
</ul>
<pre class="code"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">bertrand @ dedibox：〜$ sudo mv / etc / network / interfaces /etc/network/interfaces.old</font></font><font></font><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
bertrand @ dedibox：〜$ sudo mv etc / network / interfaces / etc / network / interfaces</font></font></pre>

</div>

<h2 class="sectionedit8" id="references"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">参考</font></font><a class="anchorjs-link " href="#references" aria-label="Anchor link for: references" data-anchorjs-icon="" style="font-family: anchorjs-icons; font-style: normal; font-variant: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h2>
<div class="level2">

<p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
- </font><a href="https://github.com/biapy/howto.biapy.com/blob/579e532edbb86c4bd41fc3c9be86c23b4d923f70/xen-tools/backup-manager.conf" class="urlextern" title="https://github.com/biapy/howto.biapy.com/blob/579e532edbb86c4bd41fc3c9be86c23b4d923f70/xen-tools/backup-manager.conf" rel="nofollow"><font style="vertical-align: inherit;">此处</font></a><font style="vertical-align: inherit;">提供</font><a href="https://github.com/biapy/howto.biapy.com/blob/579e532edbb86c4bd41fc3c9be86c23b4d923f70/xen-tools/backup-manager.conf" class="urlextern" title="https://github.com/biapy/howto.biapy.com/blob/579e532edbb86c4bd41fc3c9be86c23b4d923f70/xen-tools/backup-manager.conf" rel="nofollow"><font style="vertical-align: inherit;">了</font></a><font style="vertical-align: inherit;">备份管理器脚本</font></font><a href="https://github.com/biapy/howto.biapy.com/blob/579e532edbb86c4bd41fc3c9be86c23b4d923f70/xen-tools/backup-manager.conf" class="urlextern" title="https://github.com/biapy/howto.biapy.com/blob/579e532edbb86c4bd41fc3c9be86c23b4d923f70/xen-tools/backup-manager.conf" rel="nofollow"><font style="vertical-align: inherit;"></font></a>
</p>

</div>

<!-- cachefile /var/www/online.net/documentation.online.net/www/data/cache/5/5162103ed4202f40e27cef48062a03d0.xhtml used -->


            </div>
