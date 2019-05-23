# GraphQL-java
## 该demo主要是Java对GraphQL的实现，利用SDL进行开发，个人感觉SDL比纯Java代码实现GraphQL会更简洁明了，不会出现代码冗余的情况。本demo是基于https://www.graphql-java.com/tutorials/getting-started-with-spring-boot/ 进行的扩展延伸
### 以下是一些学习graphql的网站  
raphQL桌面调试工具
https://github.com/prisma/graphql-playground/releases/tag/v1.8.10  
GraphQL学习文档
https://www.graphql-java.com/documentation  
GraphQL中文学习官网
https://graphql.cn/learn/schema/  
GraphQL英文学习官网
https://graphql.org/learn/schema/  
schema语法规范
https://developer.github.com/v4/  
### 数据库表格及内容  
```
/*
Navicat MySQL Data Transfer

Source Server         : localhost
Source Server Version : 50726
Source Host           : localhost:3306
Source Database       : graphqltest

Target Server Type    : MYSQL
Target Server Version : 50726
File Encoding         : 65001

Date: 2019-05-23 09:10:37
*/

SET FOREIGN_KEY_CHECKS=0;

-- ----------------------------
-- Table structure for author
-- ----------------------------
DROP TABLE IF EXISTS `author`;
CREATE TABLE `author` (
  `id` varchar(64) NOT NULL,
  `first_name` varchar(255) NOT NULL,
  `last_name` varchar(255) NOT NULL,
  `create_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
  `update_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '更新时间',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- ----------------------------
-- Records of author
-- ----------------------------
INSERT INTO `author` VALUES ('author-1', 'Joanne', 'Rowling', '2019-05-22 17:03:59', '2019-05-22 17:04:30');
INSERT INTO `author` VALUES ('author-2', 'Herman', 'Melville', '2019-05-22 17:03:59', '2019-05-22 17:04:30');
INSERT INTO `author` VALUES ('author-3', 'Anne', 'Rice', '2019-05-22 17:03:59', '2019-05-22 17:04:30');
INSERT INTO `author` VALUES ('author-5', '莫言', '黄花', '2019-05-22 17:03:59', '2019-05-22 17:04:30');

-- ----------------------------
-- Table structure for book
-- ----------------------------
DROP TABLE IF EXISTS `book`;
CREATE TABLE `book` (
  `id` varchar(255) NOT NULL,
  `name` varchar(255) NOT NULL,
  `page_count` int(32) NOT NULL,
  `author_id` varchar(64) NOT NULL,
  `create_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
  `update_time` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '更新时间',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COMMENT='books';

-- ----------------------------
-- Records of book
-- ----------------------------
INSERT INTO `book` VALUES ('book-1', '哈利波特与死亡圣器', '101', 'author-1', '2019-05-22 17:05:33', '2019-05-22 17:05:33');
INSERT INTO `book` VALUES ('book-3', '人生', '500', 'author-3', '2019-05-22 17:05:33', '2019-05-22 17:05:33');
INSERT INTO `book` VALUES ('book-4', '平凡的世界', '1000', 'author-4', '2019-05-22 17:05:33', '2019-05-22 17:05:33');
INSERT INTO `book` VALUES ('book-5', '草原', '500', 'author-5', '2019-05-22 17:05:33', '2019-05-22 17:05:33');
INSERT INTO `book` VALUES ('book-6', '原野', '576', 'author-6', '2019-05-22 17:05:33', '2019-05-22 17:05:33');
INSERT INTO `book` VALUES ('book-7', '原来如初', '666', 'author-7', '2019-05-22 17:05:33', '2019-05-22 17:05:33');
INSERT INTO `book` VALUES ('book-8', '穆斯林的葬礼', '999', 'author-8', '2019-05-22 17:05:33', '2019-05-22 17:05:33');
INSERT INTO `book` VALUES ('book-9', '草根成长记（3）', '789', 'author-9', '2019-05-22 17:09:17', '2019-05-22 17:13:17');
```